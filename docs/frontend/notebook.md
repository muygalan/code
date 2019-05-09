---
layout: default
title: Notebook
parent: Front-End
nav_order: 1
---

# Notebook

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Boilerplate HTML5 Template

```
<!doctype html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <title></title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="css/style.css">
</head>

<body>
  <p>Hello world! This is HTML5 Boilerplate.</p>
 </body>

</html>
```

## Folder Structure

For larger scale projects, try implementing the following folder structure:
- `resources`
  - `/css`
    - `style.css`
    - `/img` — images pertaining to the specific webpage can be placed here.
- `/data`
- `/img` — a collective variety of images can be placed here.
- `/js`

- `/vendors` — files obtained from the internet.
  - `/css` — this is for external css stylesheet files (e.g. normalize, resets, bootstrap, grids etc.)
  - `/fonts` — specific fonts downloaded from the internet.
  - `/js`
- `index.html`

## Resets

Begin each `style.css` file with this bare minimum CSS reset:

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

## CSS Rule Arrangement

Always order your CSS rules alphabetically. 

## Define Website Base Styles

Use the `html` property for this. For fonts, use the `px` unit. Fonts used thereafter, use percentages. 

**Example:**

```
html {
  background-color: #fff;
  color: #555;
  font-family: 'Lato', 'Arial', sans-serif;
  font-size: 20px;
  font-weight: 300;
  text-rendering: optimizeLegibility;
}
```


## Sectioning your Stylesheet

```
 /* 1. Base */

 These are the styles that declare the primary colors, font sizes, 
 hyperlinks, line heights, and min-max heights.

 /* 2. Shared */

Here different selectors will share the same set of rules. 
We will extend this section as we need along the way.

/* 3. Specific */

Where we will style each element individually

/* 4. Responsiveness */

Add media queries here.

/* Main Content */

/* Footer */

/* -------------------------------------- */ 
/* HEADER */
/* -------------------------------------- */ 

/* -------------------------------------- */ 
/* REUSABLE COMPONENTS */
/* -------------------------------------- */ 

/* ----- HEADINGS ----- */ 

```

## Responsive Web Design

### Obtaining Percentages for Font-Sizes

Divide the font you want by the predefined HTML font.

**Example:**

18/20 = 0.9 or 90%

### Custom Grids

TBA

## Layout Structure

### Headers

Headers usually have a large _hero_ image with a website logo, navigation bar, and hero text box.

Example:

```
<header>
      <nav>
        <div class="row">
          <img src="resources/img/logo-white.png" alt="Omnifood logo" class="logo">
          <ul class="main-nav">
            <li><a href="#">Food delivery</a></li>
            <li><a href="#">How it works</a></li>
            <li><a href="#">Our cities</a></li>
            <li><a href="#">Sign up</a></li>
          </ul>
        </div>
      </nav>
      <div class="hero-text-box">
        <h1>Goodbye junk food.<br> Hello super healthy meals.</h1>
        <a class="btn btn-full" href="#">I’m hungry</a>
        <a class="btn btn-ghost" href="#">Show me more</a>
      </div>
    </header>
```

- Define the height of the `header`. 

Example: `height: 100vh;`

- Basic background-image template:

```
x background-image: url(img/image.jpg);
x background-size: cover;
x background-position: center;
```

The above provides a background image to your `header` that covers it in full with a centered position.

### Text Boxes