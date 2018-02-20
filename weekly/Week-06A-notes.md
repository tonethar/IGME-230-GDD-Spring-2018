# Week 6A - The Site Design Process
Today we'll be discussing the overall process for designing a site, which consists of the following phases:
1. Define the purpose
1. Consider the audience
1. Gather Ideas
1. Organize the Ideas
1. Write the Content
1. Organize the Content
1. Determine the Navigation
1. Sketch the Pages
1. Start up your computer!
1. Build Pages
1. Test
1. Iterate
1. Maintain
1. Archive

## Topics
- Site Design
- Group exercise

## Presentations
- [Site Design](../presentations/5A-Design-Process.pdf)

## Exercise
- [Site Design](../exercises/week-5/ICE-Site-Design.docx)

## Homework
- http://www.nngroup.com/articles/top-10-mistakes-web-design/

<hr><hr>

# Flexbox Notes

## I. What is Flexbox?

CSS Flexible Box Layout is a module of CSS that defines a CSS box model optimized for user interface design, and the layout of items in one dimension. In the flex layout model, the children of a flex container can be laid out in any direction, and can “flex” their sizes, either growing to fill unused space or shrinking to avoid overflowing the parent. Both horizontal and vertical alignment of the children can be easily manipulated.

- https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout

## II. Links

Let's check these out together:

- https://caniuse.com/#feat=flexbox
- https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout
- https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- https://philipwalton.github.io/solved-by-flexbox/


## III. The basics of using Flexbox

- Set a container (a parent) to [`display: flex`]() -  which means that the container behaves like a block element, and all of the child elements of that container become *flex items*. 
- Give the child elements a [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) property. The `flex` CSS property specifies how a *flex item* will grow or shrink so as to fit the space available in its flex container. This is a shorthand property that sets [`flex-grow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow), [`flex-shrink`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink), and [`flex-basis`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis)
    - think of `flex-grow` like a ratio of how much space the element wants in their container (parent)
    - `flex-shrink` is similar, except higher numbers mean that an element will shrink more than other elements do to fit in their container (parent)
		- The `flex-basis` CSS property specifies the initial main size of a flex item. This property determines the size of the content-box unless specified otherwise using [`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing).
- The flex container needs to specify whether its flex items will have a [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) of `column` (let-to-right, multiple columns) or `row` (single column, down the page). This is referred to as the **main axis** of the layout. For the desktop, we will usually use the column layout. For mobile, it is usually a row layout.
- The [`order`](https://developer.mozilla.org/en-US/docs/Web/CSS/order) property controls the order that flex items appear in their container. Items within the same container are laid out in ascending order according to their `order` values. Elements with the same order value are laid out in the order in which they appear in the source code.

## IV. "Holy Grail" Walkthrough

Here the "Holy Grail" is a 3-column layout with equal height columns and a header and footer. It will fluidly re-size on a desktop browser. Let's build this using Flexbox! You will likely be pleased and surprised how little CSS this will take.

### IV-A. 
Start files are here: [holy-grail-start.html.zip](../other-files/holy-grail-start.html.zip)

1. Walkthrough ...



## V. Mobile First, Responsive Holy Grail
Same as above, except we utilize media queries to create a "mobile first" responsive page, that changes to a single-column layout on iPads or smaller. Let's do it!

### V-A. 
Start files are here: [holy-grail-responsive-mobile-first-start.html.zip](../other-files/holy-grail-responsive-mobile-first-start.html.zip)

1. Walkthrough ...

[<-- Back to IGME-230 Schedule](../schedule.md)
