
![design](http://i.imgur.com/rYVH4Je.gif)

# Advanced CSS and stuff

## Before you write that beautiful CSS

### Normalizing your canvas
Different browsers have different base styles. To get around the issue of browsers destroying your hard work, it's wise to use normalizing methods to standardize everything. Luckily there are numerous libraries available. Here are some that I recommend:

- Link 1
- Link 2
- Link 3

**Why not reset?**
Reset removes the base styling, where normalizing the all the elements gives you a foundation to work on and apply your styles to.

### Box-sizing
As you worked with CSS, you might have noticed some quirks when dealing with a div's height and width when paddings are applied. Most commonly when working with grids.

Let's say you're working on a two column grid and you want to add padding. Woah now! Without applying box-sizing, the extra padding adds to the width. Suddenly your 50% columns become 50% + 20px if you padded a 10px padding to the sides. Now your columns are stacked on top of each other and your layout is ruined.

There must be a better wayyyy...

There is:

```css
* {
  -webkit-box-sizing: border-box;
     -moz-box-sizing: border-box;
          box-sizing: border-box;
}
```

**What does this do?**
It forces anything that adds to the element's height or width to be included in the height and width attribute. A 200px div with a 10px padding is still 200px, making it easier to work with in your UI.

## Getting started

- [Naming Conventions](url) and writing modular code
- [Selectors](that)
- [Media query](that) and responsive design
- [Positioning](that)
- [Z-index](that)
- Working with [margins](that)
- [Floats](that)
- [Backgrounds](that)
- [Sprites](that)
- [Fonts](that) on the web
