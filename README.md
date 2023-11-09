# Frontend Mentor - Four card feature section solution

This is a solution to the [Four card feature section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/four-card-feature-section-weK1eFYK). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

-   [Overview](#overview)
    -   [The challenge](#the-challenge)
    -   [Screenshot](#screenshot)
    -   [Links](#links)
-   [My process](#my-process)
    -   [Built with](#built-with)
    -   [What I learned](#what-i-learned)
-   [Author](#author)

## Overview

### The challenge

Users should be able to:

-   View the optimal layout for the site depending on their device's screen size

### Screenshot

![](https://github.com/BomanStatic/four-card-feature-section/assets/133013695/7fed5c4b-3210-462c-9e11-b11230c858d9)

### Links

-   Live Site URL: [URL](https://bomanstatic.github.io/four-card-feature-section/)

## My process

### Built with

-   Semantic HTML5 markup
-   CSS custom properties
-   CSS Grid
-   Mobile-first workflow

### What I learned

I read an article about "private" CSS custom properties and wanted to try it out on this project. Since there are four cards with different top colors, I wanted to utilize "private" custom properties. I will walk you through how I did it.

Here is a card. Each card has at least two classes: one generic class for the common card layout, and one unique class. For this card, the unique class is **card--teambuilder**:

```html
<article class="card card--teambuilder">
    <h3>Team Builder</h3>
    <p>Scans our talent network to create the optimal team for your project</p>
    <img src="./images/icon-team-builder.svg" alt="" />
</article>
```

Here is the card CSS. In it, you can see I have created a custom property. The article stated that to establish some sort of rule, you use an **\_** to identify that it's private. This is very common in programming, where private variables are often named with an underscore.

```css
.card {
    --_line-color: var(--red, red);

    padding: 2rem;
    border-radius: var(--border-radius);
    position: relative;
    overflow: hidden;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    display: grid;
    gap: 0.5rem;
}
```

Here, you can see that I change the **background-color** of the pseudo-element using the custom property I created in **.card**.

```css
.card::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 0.25rem;
    background-color: var(--_line-color);
    top: 0;
    left: 0;
}
```

Now, instead of creating an annoying class selector to style the different **background-color(s)**, I can simply change the custom property color.

```css
.card--teambuilder {
    --_line-color: var(--red, red);
}
```

## Author

-   Website - [Pontus Boman](https://bomanstatic.github.io/)
