![design](http://i.imgur.com/fnUnH7d.png)

## Working with CSS selectors

See [week 1's ](https://github.com/wdi-sf-fall/notes/tree/master/week_01_fundamentals/day_2_productivity_htmlcssbootstrap/dusk_html_css%20and%20bootstrap#css) lecture for review

### 5 Basic ways to select an element:
Because we are now wirting modular CSS, we are not going to write our global CSS inline or in the header. Instead, we all agree to link to external stylesheets.

#### Method 1: HTML element selctor
Select an element based on its element. 
```css
input {
  border-radius: 2px;
}
```
#### Method 2: Class selector
Apply a style to any element with the same class
```css
.button {
  display: inline-block;
  padding: 15px 20px;
  border-radius: 2px;
}
```
#### Method 3: ID selector
Because of CSS specifivity issues, using IDs to apply styles isn't ideal. See [#](html).
```css
#post-23 {
  border-color: red;
}
```

#### Method 4: Nested selectors
```css
header nav {
  position: fixed;
}
```

#### Method 5: Chained selectors
You can also apply styles when **ALL** the classes or IDs in the selecting statement are present. 
```css
/* select #header only when it has the class: .navigation */
#header.navigation {
  position: fixed;
}

/* select an element that has BOTH .button AND .buttonTiny */
.button.buttonTiny {
  position: fixed;
}
```

### Nifty CSS selectors

http://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048
