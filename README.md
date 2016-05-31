# css-cooldown

Css component to display cooldown pie-like overlay

Example:

http://codepen.io/hovi6337/pen/NNZzVo

## Html structure:

```html
<div class="cooldown-wrap r10deg">
  <div class="overlay-wrap">
  </div>
</div>
```

## Css
Class r10deg tells current status of cooldown in degrees (10 in this case). 360 is completely uncovered, 0 is completely covered.
You can change from square to circle simply by setting border-radius: 50% to .cooldown-wrap element.


## Animations

I haven't managed to make pure-css animations yet (you can see for yourself), but you can animate using javascript and changing rXdeg class.

## Scss

You can use compiled version or compile from scss sources.

Scss uses math functions based on article at:
https://unindented.org/articles/trigonometry-in-sass/


## Variables

```scss
$overlay-color: rgba(0, 255, 0, 0.5);
$overlay-opacity: 0.1;
```

## Customization

You can customize css by using cooldownWrap mixin and set your own overlay-color and overlay-opacity parameters:
```scss
.cooldown-basic {
    height: 100px;
    width: 100px;
    border: 1px solid black;
    display: inline-block;
    position: relative;
    .bottom {
        font-size: 14px;
        text-align: center;
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        padding: 10px;
    }
}

.cooldown-wrap {
    @extend .cooldown-basic;
    @include cooldownWrap($overlay-color, $overlay-opacity);
    &.circle {
        border-radius: 50%;
    }
    &.red {
        @include cooldownWrap(red, $overlay-opacity);
    }
    &.blue {
        @include cooldownWrap(blue, $overlay-opacity);
    }
}
```
