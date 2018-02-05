### Simple example
```css
.container {
  display: flex;
}
.container > div {
  flex: 1 1 auto;
}
```
### Container
```css
.container {

  display: flex;
  display: inline-flex;

  flex-direction: row;            /* ltr - default */
  flex-direction: row-reverse;    /* rtl */
  flex-direction: column;         /* top-bottom */
  flex-direction: column-reverse; /* bottom-top */

  flex-wrap: nowrap; /* one-line */
  flex-wrap: wrap;   /* multi-line */

  align-items: flex-start; /* vertical-align to top */
  align-items: flex-end;   /* vertical-align to bottom */
  align-items: center;     /* vertical-align to center */
  align-items: stretch;    /* same height on all (default) */

  justify-content: flex-start; /* horizontal alignment - default */
  justify-content: flex-end;
  justify-content: center;

}
```
### Child 
```css
.container > div {

  /* This: */
  flex: 1 0 auto;

  /* Is equivalent to this: */
  flex-grow: 1;
  flex-shrink: 0;
  flex-basis: auto;

  order: 1;

  align-self: flex-start;  /* left */
  margin-left: auto;       /* right */

}
```
## Tricks
### Vertical center
```css
.container {
  display: flex;
}

.container > div {
  width: 100px;
  height: 100px;
  margin: auto;
}
```
### Vertical center (2)
```css
.container {
  display: flex;
  align-items: center;     /* vertical */
  justify-content: center; /* horizontal */
}
```
### Mobile layout
```css
.container {
  display: flex;
  flex-direction: column;
}

.container > .top {
  flex: 0 0 100px;
}

.container > .content {
  flex: 1 0 auto;
}
//A fixed-height top bar
```
### Reordering
```css
.container > .top {
 order: 1;
}

.container > .bottom {
 order: 2;
}
```
### Vertical
Vertically-center all items.
```css
.container {
  align-items: center;
}
```
### Left and right
```css
.menu > .left  { align-self: flex-start; }
.menu > .right { align-self: flex-end; }
```
### Table-like
```css
.container {
  display: flex;
}

/* the 'px' values here are just suggested percentages */
.container > .checkbox { flex: 1 0 20px; }
.container > .subject  { flex: 1 0 400px; }
.container > .date     { flex: 1 0 120px; }
```
### IE 7, 8 & 9 Flexbox hack 
```css 
.flex-row {
  display: flex;
  display: inline-block\9;
  margin-bottom: -4px\9; // inline-block will have 4px space between block
}
```
### IE 10 hack 
```html
 <!--[if !IE]><!--><script>
  if (/*@cc_on!@*/false) {
    document.documentElement.className+=' ie10';
  }
</script><!--<![endif]-->
```
```css 
.ie10 .flex-row {
  display: flex;
  margin-bottom: 0;
}
```
### Android 4. Hack 
```javascript
// Fix Android 4.4 flexbox
document.addEventListener("DOMContentLoaded", function () {
  let ua = navigator.userAgent;
  if (ua.indexOf("Android 4.") > 0) {
    $(' .flex-row ').css('display','block');
    $(' .flex-row .child ').css('float','left');
  }
});
```
## More info
- [MDN: Using CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes) 
- [Ultimate flexbox cheatsheet](http://www.sketchingwithcss.com/samplechapter/cheatsheet.html)
- [Browserhacks](http://browserhacks.com/)
