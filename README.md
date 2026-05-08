# Frontend Mentor - Tech book club landing page solution

This is a solution to the [Tech book club landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/tech-book-club-landing-page-fZQidjHU73). Frontend Mentor challenges help me improve my coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

The brief for this challenge was to build out the landing page and get it look as close to the design as possible, starting with the following assets:

- Figma design file
- Mobile, tablet & desktop layouts
- Professional design system for colors, fonts, etc.
- Optimized image assets
- HTML file with pre-written content

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

![screenshot of tech book club landing page in desktop view](./screenshot.png)

### Links

- [Frontend Mentor solution](https://www.frontendmentor.io/solutions/tech-book-club-landing-page-with-anchor-positioning-4zhhAl_NwO)
- [Live site](https://sabineemden.github.io/fm-tech-book-landing-page/)

## My process

I chose this challenge to stretch my CSS layout skills and get additional practice after I completed the Frontend Mentor learning path [Building responsive layouts](https://www.frontendmentor.io/learning-paths/building-responsive-layouts--z1qCXVqkD).

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

Working through this project, I got lots of practice working with CSS pseudo-elements and positioning to create decorative backgrounds.

The most challenging one was the dark patterned background that covers the last section of the main content area and the page footer. It is similar to the light patterned background behind the page header and the hero section with the added challenge of the variable height of the footer. Both backgrounds cover the full viewport width.

I used a `::before` pseudo-element on the last section of the main content and anchor positioning with anchors on that section and on the page footer. To extend the background over the full viewport width, I added `width: 100vw`.

```html
<main>
  <!-- main page content -->
  <section class="ready">
    <!-- section content -->
  </section>
</main>
<footer class="footer">
  <!-- footer content -->
</footer>
```

```css
.ready {
  anchor-name: --ready;
}

.ready::before {
  content: "";
  background: url(./assets/images/pattern-dark-bg.svg) var(--neutral-900);
  position: absolute;
  top: anchor(--ready top);
  bottom: anchor(--footer bottom);
  width: 100vw;
  z-index: -1;
  border-top-left-radius: var(--radius-16);
  border-top-right-radius: var(--radius-16);
}

.footer {
  anchor-name: --footer;
}
```

Using `width: 100vw` causes an issue if the page has a vertical classic scrollbar. The classic scrollbar takes up space, which makes `100vw` larger than the viewport width and causes the page to overflow horizontally. This is know as the [classic scrollbar problem](https://www.smashingmagazine.com/2023/12/new-css-viewport-units-not-solve-classic-scrollbar-problem/). I solved it by setting `scrollbar-gutter: stable` on the `<html>` element.

### Continued development

This solution has a single HTML file with 304 lines of code and a single CSS style sheet with 804 lines of code. For anything more complex than this landing page, I would want to look into better organizing my code by using multiple smaller stylesheets or better tooling.

### Useful resources

- [Convert Variable Fonts Online](https://dplugins.com/convert-variable-fonts-online/) by DPlugins - This tool helped me convert the variable fonts from TTF to WOFF2.
- [Essential Visually Hidden CSS Techniques for Web Accessibility](https://www.a11y-collective.com/blog/visually-hidden/) by Team A11Y Collective - This article describes a modern CSS technique to hide content visually using clipping instead of positioning.
- [Creative list styling](https://web.dev/articles/creative-list-styling) by Michelle Barker for web.dev - This article looks at styling lists with custom markers and counters.
- [Full Bleed](https://css-tricks.com/full-bleed/) by Chris Coyier for CSS-Tricks - This article discusses techniques for having a full-width element within a constrained-width column.
- [New CSS Viewport Units Do Not Solve The Classic Scrollbar Problem](https://www.smashingmagazine.com/2023/12/new-css-viewport-units-not-solve-classic-scrollbar-problem/) by Śime Vidas for Smashing Magazine - I learned a lot about viewport units and scrollbars from this article, including how to solve the classic scrollbar problem.
- [How to add a gradient overlay to text with CSS](https://fossheim.io/writing/posts/css-text-gradient/) by Sarah L. Fossheim- This article describes how the add a gradient overlay to a text element.
- [CSS Anchor Positioning Guide](https://css-tricks.com/css-anchor-positioning-guide/) by Juan Diego Rodríguez for CSS-Tricks - This guide is a comprehensive reference for CSS anchor positioning. It's were I found out I could use two anchors for one element.

## Author

I'm an aspiring web developer and a former chemist. What I bring from chemistry to software development is a systematic approach to problem solving and the perseverance to not give up easily.

- Frontend Mentor - [@SabineEmden](https://www.frontendmentor.io/profile/SabineEmden)
- Personal Website - [Sabine Emden](https://www.sabineemden.com/)
- Mastodon - [@sabineemden](https://social.tchncs.de/@sabineemden)

## Acknowledgments

This solution uses a CSS reset based on [A Moderne CSS Reset](https://www.joshwcomeau.com/css/custom-css-reset/) by Josh Comeau.

The font families in this project are [Inter](https://fonts.google.com/specimen/Inter) and [Martian Mono](https://fonts.google.com/specimen/Martian+Mono). The fonts are licensed under the [Open Font License](https://openfontlicense.org/open-font-license-official-text/).
