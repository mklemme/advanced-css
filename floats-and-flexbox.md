# Floats, flexbox, and you

## Outcomes
- Know how to work with floating elements
- Know hot to work with flexbox

Live version: http://codepen.io/mklemme/pen/xbZMXP?editors=110
```html
<div class="box">
    <a href="#" class="left">left</a>
    <a href="#" class="right">right</a>
</div>
```
Defining our base (S)CSS styling:
```css
.box{
  background: #bb596c;
  border-radius: 4px;
  
  a{
    display: inline-block;
    padding: 10px 15px;
    background: rgba(17,17,17,.15);
    color: white;

    /* making it look good-er */
    border-radius: 4px 0 0 4px;
    text-decoration: none;
    letter-spacing: 1px;
    font-size: 11px;
    font-weight: 100;
    
    &:last-child{
      border-radius: 0 4px 4px 0;  
    }
  }/* end a */
}/* end .box */
```

## Alignment
Let's say you wanted the two `a` elements to be on opposite sides of `.box`, would you use float or flexbox?

### Method 1: Float
If you want to use float, there are a couple of things you need to add to make sure everything works the way you would want. 

```css
.box{
  a.left{
    float: left;  
  }
  a.right{
    float: right;
  }
}
```
Good news: the two `a` tags are justified within the div. Notice how the float elements don't contribute to the height of its parent container `.box`. To get around this, we have to do something called a **clearfix**:

CSS with clearfix:
```css
.box:after { 
  content: "\00A0"; /* non-breaking space unicode character */
  display: block; 
  clear: both; 
  visibility: hidden; 
  line-height: 0; 
  height: 0;
}
```
### Method 2: Flexbox
If you will be justifying elements within their parent container, it might be easier (and better) to create a series of flexbox mixins. I've created one for justifying child elements:

```css
@mixin flexbox{
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-box-direction: normal;
  -moz-box-direction: normal;
  -webkit-box-orient: horizontal;
  -moz-box-orient: horizontal;
  -webkit-flex-direction: row;
  -ms-flex-direction: row;
  flex-direction: row;
  -webkit-flex-wrap: wrap;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  -webkit-box-pack: justify;
  -moz-box-pack: justify;
  -webkit-justify-content: space-between;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-align-content: center;
  -ms-flex-line-pack: center;
  align-content: center;
  -webkit-box-align: center;
  -moz-box-align: center;
  -webkit-align-items: center;
  -ms-flex-align: center;
  align-items: center;
}
@mixin flexboxItem{
  -webkit-box-ordinal-group: 1;
  -moz-box-ordinal-group: 1;
  -webkit-order: 0;
  -ms-flex-order: 0;
  order: 0;
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  -webkit-flex: 0 1 auto;
  -ms-flex: 0 1 auto;
  flex: 0 1 auto;
  -webkit-align-self: auto;
  -ms-flex-item-align: auto;
  align-self: auto;
}
```
Check out [link](flexyboxy) for messing with flexbox in the browser

#### Using the flexbox mixin
Add this code to the end of the file:
```css
.box{
  @include flexbox;
  a{
    @include flexboxItem;
  }
}
```
## Final code

Check out the codepen for a live version you can mess with: http://codepen.io/mklemme/pen/xbZMXP?editors=110
