---
layout: default
title: Notebook
parent: HTML
nav_order: 2
---

# Notebook

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Elements

Elements are designators that define the structure and content of objects within a page. Some of the more frequently used elements include multiple levels of headings (identified as `<h1>` through `<h6>` elements) and paragraphs (identified as the `<p>` element); the list goes on to include the `<a>`, `<div>`, `<span>`, `<strong>`, and `<em>` elements, and many more.

## Tag

The use of less-than and greater-than angle brackets surrounding an element creates what is known as a tag. Tags most commonly occur in pairs of opening and closing tags. So, anchor tags will look a bit like this: `<a>`...`</a>`

## Attributes

Attributes are properties used to provide additional information about an element. The most common attributes include the `id` attribute, which _identifies_ an element; the `class` attribute, which _classifies_ an element; the `src` attribute, which specifies a source for embeddable content; and the `href` attribute, which provides a hyperlink reference to a linked resource.

## Example Hyperlink

![](../img/html-syntax-outline.png)


## Setting Up the HTML Document Structure

HTML documents are plain text documents saved with an `.html` file extension rather than a .txt file extension. All HTML documents have a required structure that includes the following declaration and elements: `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`.

The document type declaration, or `<!DOCTYPE html>`, informs web browsers which version of HTML is being used and is placed at the very beginning of the HTML document. 


Inside the `<html>` element, the `<head>` element identifies the top of the document, including any metadata (accompanying information about the page). The content inside the `<head>` element is not displayed on the web page itself. 

All of the visible content within the web page will fall within the `<body>` element.

### HTML document structure

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Hello World</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a web page.</p>
  </body>
</html>
```

## Nested Elements

When an element is placed inside of another element, also known as nested, it is a good idea to indent that element to keep the document structure well organized and legible. In the previous code, both the `<head>` and `<body>` elements were nested—and indented—inside the `<html>` element. The pattern of indenting for elements continues as new elements are added inside the `<head>` and `<body>` elements.

## Semantics

Semantics within HTML is the practice of giving content on the page meaning and structure by using the proper element. Semantic code describes the value of content on a page, regardless of the style or appearance of that content. There are several benefits to using semantic elements, including enabling computers, screen readers, search engines, and other devices to adequately read and understand the content on a web page. Additionally, semantic HTML is easier to manage and work with, as it shows clearly what each piece of content is about.

## Block vs. Inline Elements

_Block-level_ elements begin on a new line, stacking one on top of the other, and occupy any available width. Block-level elements may be nested inside one another and may wrap inline-level elements. We’ll most commonly see block-level elements used for larger pieces of content, such as paragraphs.

_Inline-level_ elements do not begin on a new line. They fall into the normal flow of a document, lining up one after the other, and only maintain the width of their content. Inline-level elements may be nested inside one another; however, they cannot wrap block-level elements. We’ll usually see inline-level elements with smaller pieces of content, such as a few words.

## Comments within HTML & CSS

HTML comments start with `<!-- and end with -->`. CSS comments start with `/*` and end with `*/`.

## Headings

Headings are block-level elements, and they come in six different rankings, `<h1>` through `<h6>`.

```
<h1>Heading Level 1</h1>
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
```

## Paragraphs

Paragraphs are defined using the `<p>` block-level element.

## Bold Text with Strong

There are two elements that will bold text for us: the `<strong>` and `<b>` elements.

The `<strong>` element is semantically used to give _strong importance_ to text, and is thus the most popular option for bolding text. The `<b>` element, on the other hand, semantically means to _stylistically_ offset text, which isn’t always the best choice for text deserving prominent attention.

## Italicize Text with Emphasis

To italicize text, thereby placing emphasis on it, we’ll use the `<em>` inline-level element. 

The `<em>` element is used semantically to place a _stressed emphasis_ on text; it is thus the most popular option for italicizing text. The other option, the `<i>` element, is used semantically to convey text in an _alternative voice or tone_, almost as if it were placed in quotation marks. 

## Building Structure

HTML5 introduced new structurally based elements, including the `<header>, <nav>, <article>, <section>, <aside>, and <footer>` elements.

![](../img/building-structure.png)

### Header

The `<header>` element, like it sounds, is used to identify the top of a page, article, section, or other segment of a page. In general, the `<header>` element may include a heading, introductory text, and even navigation.  `<header>...</header>`

### Navigation

The `<nav>` element identifies a section of major navigational links on a page. The `<nav>` element should be reserved for primary navigation sections only, such as global navigation, a table of contents, previous/next links, or other noteworthy groups of navigational links. `<nav>...</nav>`

### Article

The `<article>` element is used to identify a section of independent, self-contained content that may be independently distributed or reused. We’ll often use the `<article>` element to mark up blog posts, newspaper articles, user-submitted content, and the like.

When deciding whether to use the `<article>` element, we must determine if the content within the element could be replicated elsewhere without any confusion. If the content within the `<article>` element were removed from the context of the page and placed, for example, within an email or printed work, that content should still make sense.

### Section

The `<section>` element is used to identify a thematic grouping of content, which generally, but not always, includes a heading. The grouping of content within the `<section>` element may be generic in nature, but it’s useful to identify all of the content as related.

### Deciding Between <article>, <section>, or <div> Elements

At times it becomes fairly difficult to decide which element—`<article>`, `<section>`, or `<div>`—is the best element for the job based on its semantic meaning. The trick here, as with every semantic decision, is to look at the content.

Both the <article> and <section> elements contribute to a document’s structure and help to outline a document. If the content is being grouped solely for styling purposes and doesn’t provide value to the outline of a document, use the `<div>` element.

If the content adds to the document outline and it can be independently redistributed or syndicated, use the `<article>` element.

If the content adds to the document outline and represents a thematic group of content, use the `<section>` element.

### Aside 

The `<aside>` element holds content, such as sidebars, inserts, or brief explanations, that is tangentially related to the content surrounding it. When used within an `<article>` element, for example, the `<aside>` element may identify content related to the author of the article.

### Footer

The `<footer>` element identifies the closing or end of a page, article, section, or other segment of a page. Generally the `<footer>` element is found at the bottom of its parent. Content within the `<footer>` element should be relative information and should not diverge from the document or section it is included within.

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

