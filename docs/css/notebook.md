---
layout: default
title: Notebook
parent: CSS
nav_order: 1
---

# Notebook

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Selectors

As elements are added to a web page, they may be styled using CSS. A selector designates exactly which element or elements within our HTML to target and apply styles (such as _color, size, and position_) to.

Selectors generally target an attribute value, such as an `id` or `class` value, or target the type of element, such as `<h1>` or `<p>`.

Within CSS, selectors are followed with curly brackets, `{}`, which encompass the styles to be applied to the selected element. The selector here is targeting all `<p>` elements. `p { ... }`

## Properties

Once an element is selected, a property determines the styles that will be applied to that element. Property names fall after a selector, within the curly brackets, `{}`, and immediately preceding a colon, :. There are numerous properties we can use, such as _background, color, font-size, height, and width_, and new properties are often added. In the following code, we are defining the color and font-size properties to be applied to all `<p>` elements.

```
p {
 color: ...;
 font-size: ...;
}
```

## Values

Determine the behavior of a property. Values can be identified as the text between the colon, :, and semicolon, ;. Here we are selecting all `<p>` elements and setting the value of the color property to be orange and the value of the font-size property to be 16 pixels.

![](../img/css-syntax-outline.png)

## Type Selectors

_Type_ selectors target elements by their element type. For example, should we wish to target all division elements, `<div>`, we would use a type selector of div.  `div { ... }`

## Class Selectors

`Class` selectors allow us to select an element based on the element’s **class** attribute value. Class selectors are a little more specific than type selectors, as they select a particular group of elements rather than all elements of one type.

Class selectors allow us to apply the same styles to different elements at once by using the same **class** attribute value across multiple elements. Within CSS, classes are denoted by a leading period, ., followed by the **class** attribute value.   `.awesome { ... }`

## ID Selectors

ID selectors are even more precise than class selectors, as they target only one unique element at a time. Just as class selectors use an element’s **class** attribute value as the selector, ID selectors use an element’s id attribute value as a selector.

Regardless of which type of element they appear on, **id** attribute values can only be used once per page. If used they should be reserved for significant elements.

Within CSS, ID selectors are denoted by a leading hash sign, **#**, followed by the id attribute value.  `#shayhowe { ... }`

## Referencing CSS

The best practice for referencing our CSS is to include all of our styles in a single external style sheet, which is referenced from within the `<head>` element of our HTML document.

```
<head>
  <link rel="stylesheet" href="main.css">
</head>
```

## CSS Resets

Every web browser has its own default styles for different elements. How Google Chrome renders headings, paragraphs, lists, and so forth may be different from how Internet Explorer does. To ensure cross-browser compatibility, CSS resets have become widely used.

CSS resets take every common HTML element with a predefined style and provide one unified style for all browsers. These resets generally involve removing any sizing, margins, paddings, or additional styles and toning these values down. Because CSS cascades from top to bottom our reset needs to be at the very top of our style sheet.

## Comments within HTML & CSS

HTML comments start with `<!-- and end with -->`. CSS comments start with `/*` and end with `*/`.

## Specificity Weight

The type selector has the lowest specificity weight and holds a point value of **0-0-1**. 
The class selector has a medium specificity weight and holds a point value of **0-1-0**. 
Lastly, the ID selector has a high specificity weight and holds a point value of **1-0-0**.

## Key Selector

When selectors are combined they should be read from right to left. The selector farthest to the right, directly before the opening curly bracket, is known as the _key selector_. The key selector identifies exactly which element the styles will be applied to. Any selector to the left of the key selector will serve as a _prequalifier_.

**Example:** 

```
.hotdog p {
  background: brown;
}
.hotdog p.mustard {
  background: yellow;
}
```

Reading the combined selector from right to left, it is targeting paragraphs with a class attribute value of `mustard` that reside within an element with the class attribute value of `hotdog`.

## Specificity Within Combined Selectors

Looking at our combined selectors from before, the first selector, .hotdog p, had both a class selector and a type selector. Knowing that the point value of a class selector is 0-1-0 and the point value of a type selector is 0-0-1, the total combined point value would be 0-1-1, found by adding up each kind of selector.

The second selector, .hotdog p.mustard, had two class selectors and one type selector. Combined, the selector has a specificity point value of 0-2-1. The 0 in the first column is for zero ID selectors, the 2 in the second column is for two class selectors, and the 1 in the last column is for one type selector.


## Colors

Currently there are four primary ways to represent sRGB colors within CSS: keywords, hexadecimal notation, and RGB and HSL values.

### RGB Colors

RGB color values are stated using the `rgb()` function, which stands for red, green, and blue. The function accepts three comma-separated values, each of which is an integer from `0` to `255`. A value of `0` would be pure black; a value of `255` would be pure white. `rgb(255, 102, 0)`.

### RGB Alpha

RGB color values may also include an _alpha_, or transparency, channel by using the `rgba()` function. The `rgba()` function requires a fourth value, which must be a number between `0` and `1`, including decimals. A value of `0` creates a fully transparent color, meaning it would be invisible, and a value of `1` creates a fully opaque color. Any decimal value in between `0` and `1` would create a semi-transparent color.

If we wanted our shade of orange to appear 50% opaque, we would use an RGBa color value of `rgba(255, 102, 0, .5)`.

maroon background color to 25% opaque

```
.task {
  background: rgba(128, 0, 0, .25);
}

yellow background color 100% opaque


.count {
  background: rgba(255, 255, 0, 1);
}
```

### HSL & HSLa Colors

HSL color values are stated using the `hsl()` function, which stands for hue, saturation, and lightness. Within the parentheses, the function accepts three comma-separated values, much like `rgb()`.

<img src="../img/css-colors-hsl.png" alt="drawing" width="350"/><img src="../img/css-colors-hsla.png" alt="drawing" width="350"/>

The first value, the hue, is a unitless number from `0` to `360`. The numbers `0` through `360` represent the color wheel, and the value identifies the degree of a color on the color wheel.

The second and third values, the saturation and lightness, are percentage values from `0` to `100%`. The saturation value identifies how saturated with color the hue is, with `0` being grayscale and `100%` being fully saturated. The lightness identifies how dark or light the hue value is, with `0` being completely black and `100%` being completely white.

```
.task {
  background: hsl(0, 100%, 25%);
}
.count {
  background: hsl(60, 100%, 50%);
}
```

**HSL** color values, like **RGBa**, may also include an alpha, or transparency, channel with the use of the `hsla()` function. The behavior of the alpha channel is just like that of the `rgba()` function. A fourth value between `0` and `1`, including decimals, must be added to the function to identify the degree of opacity.

Our shade of orange as an HSLa color set to 50% opaque would be represented as `hsla(24, 100%, 50%, .5)`

## Lengths

### Absolute Lengths

Absolute length values are the simplest length values, as they are fixed to a physical measurement, such as inches, centimeters, or millimeters. The most popular absolute unit of measurement is known as the pixel and is represented by the `px` unit notation.

### Pixels

The pixel is equal to 1/96th of an inch; thus there are 96 pixels in an inch. The exact measurement of a pixel, however, may vary slightly between high-density and low-density viewing devices.

```
p {
  font-size: 14px;
}
```

### Relative Lengths

In addition to absolute length values, there are also relative length values. Relative length values are a little more complicated, as they are not fixed units of measurement; they rely on the length of another measurement.

### Percentages

Percentages, represented by the `%` unit notation, are one of the most popular relative values. Percentage lengths are defined in relation to the length of another object. For example, to set the `width` of an element to `50%`, we have to know the width of its parent element, the element it is nested within, and then identify `50%` of the parent element’s width.

```
.col {
  width: 50%;
}
```

Here we’ve set the width of the element with the class attribute value of `col` to `50%`. That `50%` will be calculated relative to the width of the element’s parent.

### Em

The `em` unit is also a very popular relative value. The `em` unit is represented by the `em` unit notation, and its length is calculated based on an element’s font size.

A single em unit is equivalent to an element’s font size. So, for example, if an element has a font size of `14` pixels and a `width` set to `5em`, the width would equal `70` pixels (14 pixels multiplied by 5).

```
.banner {
  font-size: 14px;
  width: 5em;
}
```

When a font size is not explicitly stated for an element, the em unit will be relative to the font size of the closest parent element with a stated font size.


## Display

Exactly how elements are displayed—as block-level elements, inline elements, or something else—is determined by the `display` property. Every element has a default display property value; however, as with all other property values, that value may be overwritten. There are quite a few values for the `display` property, but the most common are `block, inline, inline-block`, and `none`.

```
p {
  display: block;
}

p {
  display: inline;
}

p {
  display: inline-block;
}
```

### Block

Block-level elements begin on a new line, stacking one on top of the other, and occupy any available width. Block-level elements may be nested inside one another and may wrap inline-level elements. We’ll most commonly see block-level elements used for larger pieces of content, such as paragraphs.

### Inline

Inline-level elements do not begin on a new line. They fall into the normal flow of a document, lining up one after the other, and only maintain the width of their content. Inline-level elements may be nested inside one another; however, they cannot wrap block-level elements. We’ll usually see inline-level elements with smaller pieces of content, such as a few words.

### Inline-Block

Things get interesting with the `inline-block` value. Using this value will allow an element to behave as a block-level element, accepting all box model properties. However, the element will be displayed in line with other elements, and it will not begin on a new line by default.

## Box Model

According to the box model concept, every element on a page is a rectangular box and may have width, height, padding, borders, and margins.

![](../img/css-boxmodel.png)

Each part of the box model corresponds to a CSS property: `width, height, padding, border`, and `margin`.

## Calculate Width & Height

According to the box model, the total width of an element can be calculated using the following formula:

`margin-right + border-right + padding-right + width + padding-left + border-left + margin-left`

In comparison, according to the box model, the total height of an element can be calculated using the following formula:

`margin-top + border-top + padding-top + height + padding-bottom + border-bottom + margin-bottom`

![](../img/css-boxmodel-img2.png)

Using the formulas, we can find the total height and width of our example code.

**Width:** 492px = 20px + 6px + 20px + 400px + 20px + 6px + 20px

**Height:** 192px = 20px + 6px + 20px + 100px + 20px + 6px + 20px

The box model is without question one of the more confusing parts of HTML and CSS. We set a `width` property value of `400` pixels, but the actual width of our element is `492` pixels. By default the box model is additive; thus to determine the actual size of a box we need to take into account padding, borders, and margins for all four sides of the box. Our width not only includes the `width` property value, but also the size of the left and right padding, left and right borders, and left and right margins.

## Width

The default width of an element depends on its display value. Block-level elements have a default width of `100%`, consuming the entire horizontal space available. _Inline_ and _inline-block_ elements expand and contract horizontally to accommodate their content. Inline-level elements cannot have a fixed size, thus the `width` and `height` properties are only relevant to non-inline elements. To set a specific width for a non-inline element, use the width property:

```
div {
  width: 400px;
}
```

## Height

The default height of an element is determined by its content. An element will expand and contract vertically as necessary to accommodate its content. To set a specific height for a non-inline element, use the `height` property:

```
div {
  height: 100px;
}
```

## Sizing Inline-Level Elements

Please keep in mind that inline-level elements will not accept the `width` and `height` properties or any values tied to them. Block and inline-block elements will, however, accept the `width` and `height` properties and their corresponding values.

## Margin

The `margin` property allows us to set the amount of space that surrounds an element. Margins for an element fall outside of any border and are completely transparent in color. Margins can be used to help position elements in a particular place on a page or to provide breathing room, keeping all other elements a safe distance away. Here’s the `margin` property in action:

```
div {
  margin: 20px;
}
```

One oddity with the `margin` property is that vertical margins, `top` and `bottom`, are not accepted by inline-level elements. These vertical margins are, however, accepted by block-level and inline-block elements.

## Padding

The `padding` property is very similar to the margin property; however, it falls inside of an element’s border, should an element have a border. The `padding` property is used to provide spacing directly within an element. Here’s the code:

```
div {
  padding: 20px;
}
```

The `padding` property, unlike the `margin` property, works vertically on inline-level elements. This vertical `padding` may blend into the line above or below the given element, but it will be displayed.

## Margin & Padding on Inline-Level Elements

Inline-level elements are affected a bit differently than block and inline-block elements when it comes to margins and padding. Margins only work horizontally—**left** and **right**—on inline-level elements. Padding works on all four sides of inline-level elements; however, the vertical padding—the **top** and **bottom**—may bleed into the lines above and below an element.

Margins and padding work like normal for block and inline-block elements.


## Margin & Padding Declarations

Using the `margin` or `padding` property alone, with any number of values, is considered shorthand. With longhand, we can set the value for one side at a time using unique properties. Each property name (in this case margin or padding) is followed by a dash and the side of the box to which the value is to be applied: `top, right, bottom, or left`. For example, the padding-left property accepts only one value and will set the **left** padding for that element; the `margin-top` property accepts only one value and will set the top margin for that element.

```
div {
  margin: 10px 20px 0 15px;
}

div {
  margin-top: 10px;
  padding-left: 6px;
}
```

## Borders

Borders fall between the padding and margin, providing an outline around an element. The `border` property requires three values: `width, style, and color`. Shorthand values for the border property are stated in that order—`width, style, color`. In longhand, these three values can be broken up into the `border-width, border-style, and border-color` properties. These longhand properties are useful for changing, or overwriting, a single border value.

Borders can have different appearances. The most common style values are `solid, double, dashed, dotted, and none`, but there are several others to choose from.

```
div {
  border: 6px solid #949599;
}
```

## Individual Border Sides

As with the `margin` and `padding` properties, borders can be placed on one side of an element at a time if we’d like. Doing so requires new properties: `border-top, border-right, border-bottom, and border-left`. The values for these properties are the same as those of the `border` property alone: `width, style, and color`. If we want, we can make a border appear only on the bottom of an element:

```
div {
  border-bottom: 6px solid #949599;
}
```

Additionally, styles for individual border sides may be controlled at an even finer level. For example, if we wish to change only the `width` of the bottom border we can use the following code:

```
div {
  border-bottom-width: 12px;
}
```

These highly specific longhand border properties include a series of hyphen-separated words starting with the border base, followed by the selected side—`top, right, bottom, or left`—and then `width, style, or color`, depending on the desired property.

## Border Radius

Enables us to round the corners of an element. 

The border-radius property accepts length units, including percentages and pixels, that identify the radius by which the corners of an element are to be rounded. A single value will round all four corners of an element equally; two values will round the `top-left/bottom-right` and `top-right/bottom-left` corners in that order; four values will round the `top-left, top-right, bottom-right, and bottom-left` corners in that order.

```
div {
  border-radius: 5px;
}
```

The `border-radius` property may also be broken out into longhand properties that allow us to change the radii of individual corners of an element. These longhand properties begin with `border`, continue with the corner’s vertical location (`top or bottom`) and the corner’s horizontal location (`left or right`), and then end with radius. For example, to change the top-right corner radius of a `<div>`, the `border-top-right-radius` property can be used.

```
div {
  border-top-right-radius: 5px;
}
```

## Box Sizing 

Until now the box model has been an additive design. CSS3 introduced the `box-sizing` property, which allows us to change exactly how the box model works and how an element’s size is calculated. The property accepts three primary values—`content-box, padding-box, and border-box`—each of which has a slightly different impact on how the box size is calculated.

## Content Box

The `content-box` value is the default value, leaving the box model as an additive design. If we don’t use the `box-sizing` property, this will be the default value for all elements. The size of an element begins with the `width` and `height` properties, and then any `padding, border, or margin` property values are added on from there.

```
div {
  -webkit-box-sizing: content-box;
     -moz-box-sizing: content-box;
          box-sizing: content-box;
}
```

## Browser-Specific Properties & Values

As CSS3 was introduced, browsers gradually began to support different properties and values, including the `box-sizing` property, by way of vendor prefixes. Vendor prefixes may be seen on both properties and values, all depending on the CSS specification.

When a property or value needs a vendor prefix, the prefix will only be used in the introduction of that property or value (in the interest of keeping our code digestible and concise).

For reference, the most common vendor prefixes are outlined here:

Mozilla Firefox: `-moz-`
Microsoft Internet Explorer: `-ms-`
Webkit (Google Chrome and Apple Safari): `-webkit-`

## Border Box

The `border-box` value alters the box model so that any `border` or `padding` property values are included within the `width` and `height` of an element. When using the `border-box` value, if an element has a `width` of `400` pixels, a padding of `20` pixels around every side, and a `border` of `10` pixels around every side, the actual width will remain `400` pixels.

If we add a `margin`, those values will need to be added to calculate the full `box size`. No matter which box-sizing property value is used, any margin values will need to be added to calculate the full size of the element.

![](../img/css-box-sizing.png)

## Universal Selector

In CSS the asterisk, `*`, is the **universal selector**, which selects every element. Rather than listing every single element imaginable, we can use the asterisk as a catch-all to select all elements for us.

The `:before` and `:after` pseudo-elements also mentioned in this step are elements that can be dynamically generated with CSS. When using the universal selector it’s a good practice to also include these pseudo-elements in case they should ever appear.

## Float

One way to position elements on a page is with the `float` property. The `float` property allows us to take an element, remove it from the normal flow of a page, and position it to the left or right of its parent element. All other elements on the page will then flow around the floated element. An `<img>` element floated to the side of a few paragraphs of text, for example, will allow the paragraphs to wrap around the image as necessary.

The float property accepts a few values; the two most popular values are `left` and `right`, which allow elements to be floated to the left or right of their parent element.

```
img {
  float: left;
}
```

For reference, when an element is floated, it will float all the way to the edge of its parent element. If there isn’t a parent element, the floated element will then float all the way to the edge of the page.

When we float an element, we take it out of the normal flow of the HTML document. This causes the width of that element to default to the width of the content within it. Sometimes, such as when we’re creating columns for a reusable layout, this behavior is not desired. It can be corrected by adding a fixed `width` property value to each column. Additionally, to prevent floated elements from touching one another, causing the content of one to sit directly next to the content of the other, we can use the `margin` property to create space between elements.

## Clearing Floats

Clearing floats is accomplished using the `clear` property, which accepts a few different values: the most commonly used values being `left, right, and both`.

```
div {
  clear: left;
}
```

The `left` value will clear left floats, while the `right` value will clear right floats. The both value, however, will clear `both` left and right floats and is often the most ideal value.

## Containing Floats

Rather than clearing floats, another option is to contain the floats. The outcomes of containing floats versus those of clearing them are nearly the same; however, containing floats does help to ensure that all of our styles will be rendered properly.

To contain floats, the floated elements must reside within a parent element. The parent element will act as a container, leaving the flow of the document completely normal outside of it. The CSS for that parent element, represented by the `group` class below, is shown here:

```
.group:before,
.group:after {
  content: "";
  display: table;
}
.group:after {
  clear: both;
}
.group {
  clear: both;
  *zoom: 1;
}
```

There’s quite a bit going on here, but essentially what the CSS is doing is clearing any floated elements within the element with the class of `group` and returning the flow of the document back to normal.

More specifically, the `:before` and `:after` pseudo-elements, as mentioned in the Lesson 4 exercise, are dynamically generated elements above and below the element with the class of `group`. Those elements do not include any content and are displayed as `table`-level elements, much like block-level elements. The dynamically generated element after the element with the class of `group` is clearing the floats within the element with the class of `group`, much like the `clear` from before. And lastly, the element with the class of `group` itself also clears any floats that may appear above it, in case a left or right float may exist. It also includes a little trickery to get older browsers to play nicely.

It is more code than the `clear: both`; declaration alone, but it can prove to be quite useful.

## Positioning with Inline-Block

n addition to using floats, another way we can position content is by using the display property in conjunction with the inline-block value. [Read more](https://learn.shayhowe.com/html-css/positioning-content/#inline-block)

## Position

The `position` property identifies how an element is positioned on a page and whether or not it will appear within the normal flow of a document. This is used in conjunction with the box offset properties—`top, right, bottom, and left`—which identify exactly where an element will be positioned by moving elements in a number of different directions.

By default every element has a `position` value of `static`, which means that it exists in the normal flow of a document and it doesn’t accept any box offset properties. The `static` value is most commonly overwritten with a `relative` or `absolute` value, which we’ll examine next.

## Relative Positioning
