# Negative margins
http://codepen.io/mklemme/pen/gbPyRX?editors=110  
http://www.smashingmagazine.com/2009/07/27/the-definitive-guide-to-using-negative-margins/

Long story short:
If you apply a negative margin to the top or left, it moves the element in that direction. If you use it on the bottom or right, it pulls the objects to it. Weird, huh?

## Collapsing margins. What?
Collapsing margins is a funky, initially unintuitive, quirk that occurs when two margin declarations touch. The highest margin wins.

This was implimented by W3C to make sure that elements with no content or height do not add to the margin.

Codepen example: http://codepen.io/mklemme/pen/KwVYar?editors=110

Situations where the margins are not collapsed:
- floated elements
- absolutely positioned elements
- inline-block elements
- elements with the overflow property of anything other than visible
- elements that have had their float cleared

**Further reading** This is confusing, I know. If you would like to know more, check out this Sitepoint article:http://www.sitepoint.com/web-foundations/collapsing-margins/
