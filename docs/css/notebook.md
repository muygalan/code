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

### Inline

### Inline-Block

Things get interesting with the `inline-block` value. Using this value will allow an element to behave as a block-level element, accepting all box model properties. However, the element will be displayed in line with other elements, and it will not begin on a new line by default.

## Box Model

According to the box model concept, every element on a page is a rectangular box and may have width, height, padding, borders, and margins.

![](../img/css-boxmodel.png)

Each part of the box model corresponds to a CSS property: `width, height, padding, border`, and `margin`.