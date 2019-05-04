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

- `/css`
  - `style.css`
  - `/img`
- `/data`
- `/img`
- `/js`

- `/vendors`
  - `/css` — this is for external css stylesheet files (e.g. normalize, resets, bootstrap, grids etc.)
  - `/fonts`
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

```


