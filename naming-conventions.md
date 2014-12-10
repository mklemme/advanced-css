![computer](http://media.giphy.com/media/vjmSleUsnXU8o/giphy.gif)
## Rethinking CSS style names for developers who want to write more modular code and do other developer stuff good too

> Inspirational text about why you should care. Because if you don't care about your code, who will?  
> \- Some web developer

TL;DR - Create styles that compartmentalize your CSS with layout and appearance styling

### Outcomes
- Identify different types of naming conventions
- Write modular css styles and

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

## Writing modular CSS code

Modular code is code that is easily reusable in the contraints you define. 

Transform your old legacy code:
```html
<div>  
  <h1>Features of the w3resource JavaScript tutorials</h1>  
  <p>Aurhor :  Rameshwar Ghosh</p>  
  <p>This article has received 7 likes in facebook and received 3 google plus.</p>  
</div>
```
into this:
```html
<article itemscope itemtype="http://schema.org/Article" class="post">  
  <span itemprop="name" class="post-title">Features of the w3resource JavaScript tutorials</span>  
  by <span itemprop="author" class="post-author">Rameshwar Ghosh</span>  
  This article has received 7 likes in facebook and received 3 google plus.  
  <meta itemprop="interactionCount" content="FacebookLikes:7"/>  
  <meta itemprop="interactionCount" content="GooglePlus:3"/>  
</article>
```

### Why care?
I'll tell you why: modular code makes designing your page easier. Since you define a set of standards as you develop your app, you don't spend a lot of time on what css names to use and when. An article on one page has the same css and html markup as an article on another page. It is totally fine to override code as you go if you need changes specific to a page.

### Modular code and scope
Shifting your workflow from designing per page to designing for the UI, designing interfaces become streamlined. Since you're reusing a lot of styles, you don't need to keep defining redundant code.

### Best practices
This is more subjective since it varies from developer to developer, but it generally helps to recognize when CSS is becoming redundant. Think DRY!

Libraries like SASS/SCSS/LESS make it easy to write modular CSS code by using their mixins and variables. You can also do math and other functions inside your SASS file.

If you're feeling frisky, look Polymer for create usable html templates that you can use throughout your application.

