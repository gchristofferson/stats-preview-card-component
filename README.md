# Frontend Mentor - Stats preview card component solution

This is a solution to the [Stats preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/stats-preview-card-component-8JqbgoU62). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

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

Users should be able to:

- View the optimal layout depending on their device's screen size

### Screenshot

![](./images/screenshot.jpg)


### Links

- Solution URL: [https://github.com/gchristofferson/stats-preview-card-component](https://github.com/gchristofferson/stats-preview-card-component)
- Live Site URL: [https://stats-preview-card-component-ten-gilt.vercel.app/](https://stats-preview-card-component-ten-gilt.vercel.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow


### What I learned

Although I've used the background-blend-mode property before, in this project I took a little more time to understanding how to use it to blend a background image with a colorful overlay.  I also used the mix-blend-mode to reduce the contrast as well as lighten the image.  Lastly, I tweaked the colors hsl values to brighten the overlay color.  I haven't used hsl() for colors in any of my previous projects, but now I see the value in using them as they allow for a different degree of fine-tuning with color values.

Below is the div I applied the background-image and background-blend-mode to:

```html
<div class="card__img"></div>
```
At first, I didn't completely understand how to blend a background color and a background image, and in my first solution I used a linear-gradient.  This solution worked though, because gradients and images occupy the same background "space". Here are the styles I used at first (for mobile layout):
```css
.card__img {
    width: 325px;
    height: 240px;
    border-radius: 10px 10px 0 0;
    background-size: cover;
    background-image: url("../images/image-header-mobile.jpg"),
    linear-gradient(var(--accent), var(--accent));
    background-blend-mode: multiply;
    order: -1;
}
```
However, since background-color and background-image live in different layers, I decided to use the following styles in my final solution instead:
```css
.card__img {
  width: 325px;
  height: 240px;
  border-radius: 10px 10px 0 0;
  background-size: cover;
  background-image: url("../images/image-header-mobile.jpg");
  background-color: hsl(273, 97%, 64%);
  background-blend-mode: multiply;
  mix-blend-mode: exclusion;
  order: -1;
}
```
The visual effect is the same, but I believe this code is a bit more explicit and readable.

### Continued development

In future projects I will explore background-blend-modes further to make sure I'm following best practices when using this technique.  I also want to learn more about how to use the related mix-blend-mode to create appealing visual effects.  Mix-blend-modes could have come in handy for a previous project I did where I needed the text color for a button to be the same as the card's background.  I ended up writing 3 different styles for 3 buttons which were each on differently colored backgrounds.  I'm sure I could have used the mix-blend-mode to write one reusable style instead. I'm going to explore this technique more in future projects.

### Useful resources

- [https://highrise.digital/blog/css-blend-modes/](https://highrise.digital/blog/css-blend-modes/) - This is an amazing article which helped me finally understand background-blend-modes and how to use them.   I'd recommend it to anyone still learning this concept. It also explains the mix-blend-mode.

## Author

- Frontend Mentor - [@gchristofferson](https://www.frontendmentor.io/profile/gchristofferson)
- Twitter - [@GreggChristoff2](https://twitter.com/GreggChristoff2)

## Acknowledgments

I want to thank [@kens-visuals](https://www.frontendmentor.io/profile/kens-visuals) for his tips on fixing the accessibility issues I had at first as well as in helping me improve the background color by applying it to the body instead of the card's container. 

I also want to tip my hat to [@markup-mitchell](https://www.frontendmentor.io/profile/markup-mitchell) who was key in helping me understand how to blend an image and background color and who inspired me to dive deeper into using hsl() color values.T