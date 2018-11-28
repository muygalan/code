---
layout: default
title: Bulma Setup
parent: Bulma
nav_order: 1
---

# Bulma Setup

## Download Method 1

If you have **node** installed on your computer, you can simply run the following command in your terminal within your desired folder:

```
npm install bulma
```

## Download Method 2

Visit Bulma's [official website](https://bulma.io/){:target="_blank"} and click the download button to download the zip file.

## Configuring your Bulma setup for usage

> 1. Create a new project folder with the following directories and files: **/css**, **/js**, and **index.html**
>
> 2. The next steps instruct you on how to copy & paste files from your Bulma download folder to your project folder. 

After downloading the Bulma files, copy the `bulma.min.css` file from the **/css** folder to your project's **/css** folder.

### Installing Font Awesome (optonal)

1. Visit [Font Awesome](http://www.fontawesome.com){:target="_blank"} and click the **For the Web** button to download the zip.

2. Unzip the file, enter the **/js** folder, and copy the **all.js** file into your project's **/js** folder. 

## Boilerplate Templates

Copy and paste either template into your **index.html** file.

### Boilerplate (Relative Links)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Hello Bulma!</title>
    <link rel="stylesheet" type="text/css" href="css/bulma.min.css">
    <script defer src="js/all.js"></script>
  </head>
  <body>
  <section class="section">
    <div class="container">
      <h1 class="title">
        Hello World
      </h1>
      <p class="subtitle">
        My first website with <strong>Bulma</strong>!
      </p>
    </div>
  </section>
  </body>
</html>
```

### Boilerplate (Absolute Links)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Hello Bulma!</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.2/css/bulma.min.css">
    <script defer src="https://use.fontawesome.com/releases/v5.3.1/js/all.js"></script>
  </head>
  <body>
  <section class="section">
    <div class="container">
      <h1 class="title">
        Hello World
      </h1>
      <p class="subtitle">
        My first website with <strong>Bulma</strong>!
      </p>
    </div>
  </section>
  </body>
</html>
```