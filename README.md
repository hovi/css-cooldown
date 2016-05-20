# css-cooldown
Css component to display cooldown pie-like overlay

Example:

http://codepen.io/hovi6337/pen/NNZzVo

## Html structure:
<div class="cooldown-wrap r10deg">
  <div class="overlay-wrap">
      <div class="q1"></div>
      <div class="q2"></div>
      <div class="q3"></div>
      <div class="q4"></div>
  </div>
</div>

## Css
Class r10deg tells current status of cooldown in degrees (10 in this case). 360 is completely uncovered, 0 is completely covered.
You can change from square to circle simply by setting border-radius: 50% to .cooldown-wrap element.


## Scss

You can use compiled version or compile from scss sources.

Scss uses math functions based on article at:
https://unindented.org/articles/trigonometry-in-sass/

TODO: calculate maximum possible border-width necessary based on tan(1deg) value.

## Variables: 
$overlay-color: rgba(0, 255, 0, 0.5);
$overlay-opacity: 0.1;