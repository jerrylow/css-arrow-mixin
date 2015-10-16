# CSS Arrow Mixin

A mixin to generate CSS arrows with borders. Flexible direction and positioning of the arrow.

## Options

Here are the options you pass to the mixin in order.

### Height

`size` `default: 10px`

Define the height of the arrow itself, this does not include the border size.

### Border

`size` `default: 2px`

Define the width of the border on top of the arrow. To not have a border set this to 0.

### Color

`hex or rgb/rgba` `default: #efefef`

Define the color of the arrow itself.

### Border Color

`hex or rgb/rgba` `default: #999`

Define color of the border. If you have no borders the color wouldn't matter but you can use `none` if you want.

### Direction

`top,left,right,bottom` `default: bottom`

The direction you want the arrow to be relative to the parent element.

### Outside

`boolean` `default: true`

By default the arrow is outside of the box and pointing away from its container. Setting this to `false` would set the arrow inside its container pointing to the center of the container.

## Note

When adding this mixing to an element the parent element will be set to `position: relative` to position the arrow. If you need to use anything other than relative you should create another wrapper around the arrow container.

## Example

**[CodePen Examples](http://codepen.io/jerrylow/pen/RWrWvw)**

All examples are based off of a div with the class .arrow:

```html
<div class="arrow">Lorem Ipsum</div>
```
```css
.arrow {
  border: 3px solid #97d4e8;
  border-radius: 4px;
  background: #c8e7f1;
  color: #2d7187;
  margin: 0 auto 40px;
  padding: 20px;
  text-align: center;
  width: 200px;
}
```

### Outside

![alt text](http://jerrylow.com/css-arrow-mixin/css-arrow-outside.jpg "CSS Arrow Mixin Outside")

```CSS
/* Top */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, top);
}

/* Right */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, right);
}

/* Bottom */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, bottom);
}

/* Left */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, left);
}
```

### Inside

![alt text](http://jerrylow.com/css-arrow-mixin/css-arrow-inside.jpg "CSS Arrow Mixin Inside")

```CSS
/* Top */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, top, false);
}

/* Right */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, false);
}

/* Bottom */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, false);
}

/* Left */
.arrow {
  @include css-arrow(10px, 3px, #c8e7f1, #97d4e8, false);
}
```

### No Borders

![alt text](http://jerrylow.com/css-arrow-mixin/css-arrow-no-border.jpg "CSS Arrow Mixin No Borders")

```CSS
/* No Borders Outside */
.arrow {
  @include css-arrow(10px, 0, #c8e7f1);
  border: none;
}

/* No Borders Inside */
.arrow {
  @include css-arrow(10px, 0, white, none, bottom, false);
  border: none;
}
```
