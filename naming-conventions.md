![computer](http://media.giphy.com/media/vjmSleUsnXU8o/giphy.gif)
## Rethinking CSS style names for developers who want to write more modular code and do other developer stuff good too

> Inspirational text about why you should care. Because if you don't care about your code, who will?  
> \- Some web developer

TL;DR - Create styles that compartmentalize your CSS with layout and appearance styling

### Overview:  

CSS is a series of components. Each defines a set of reusable styles that when combined, form elements in your UI. You already have an example of this in Bootstrap:

```html
<div class="progress">
  <div class="progress-bar progress-bar-success progress-bar-striped">
    <span class="sr-only">40% Complete (success)</span>
  </div>
</div>
```

Since `progress-bar` applies all the necessary base layout styling to make our progress bar appear correctly, we can now modify the appearance by adding `progress-bar-success` and `progress-bar-striped` which only overrides specific styles, e.g. any colors or animations.

#### Contents

- top-level 
- variants
- parent & children elements
- subclasses
- modifiers

### Top-level

Top level elements are the most basic form of CSS styling. These define the base styles that are global to the site. This can include `h1,h2,h3..h6` or `li,ul,figure` etc.

Notice in the example for buttons how we do not define any styles that effect color:
```css
.button {
  display: inline-block;
  padding: 15px 20px;
  border-radius: 2px;
}
```
Coupled with the neccesary html:
```html
<a href="http://example.com" class="button">Example.com</a>
```

### Variants
```css
.buttonLoud {
  background: #739ECF;
  text-transform: uppercase;
}
```
### Parent & children elements (nested)
```css
article{}
.articleTitle{}
.articleAuthor
```
### Subclasses
```css
.input {
  padding: 10px
}

.inputDropdown {
  &:after{
    content: "\25BE";
  }
}
```

### Modifiers
```css
.button.disabled{
  cursor:not-allowed;
}
```
These can also be helper classes:
```css
.text-right {
  text-align: right;
}

.inline-block {
  display: inline-block;
}
```
