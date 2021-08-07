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

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size

### Screenshot

![](./screenshot-01.png)

### Links

- Solution URL: [Add solution URL here](https://github.com/dan-dye/stats-preview-card-component)
- Live Site URL: [Add live site URL here](https://dan-dye.github.io/stats-preview-card-component/)

## My process

### Built with

- Semantic HTML5 markup
- Flexbox

### What I learned

This was a good project for getting to practice using flexbox for responsive styling. Starting with a layout already in mind was good practice for visualizing how to structure flex containers. I also found it was suprisingly challenging working to recreate a provided layout compared to making the layout as I go as I normally would for a project. I found most of my time was taken up tweaking elements to match the specifications. 

One major hurdle I had was matching the color filter on the card's image. Since it was monotone I couldn't adjust the hue using a filter so I also tried setting the color to a background image and then turning down the opacity on the main image to let the color through. This worked okay, but I found the shaded areas of the photo lost a noticeable degree of darkness as the opacity was lowered and would tend to wash out with the saturated purple color. Similarly raising the opacity on the front image lost too much saturation as it got closer to the original black and white image. 

I eventually found this [resource](https://alligator.io/css/exploring-blend-modes/) that discussed the use of mix-blend-mode which provided a result much closer to the original design by providing the saturated purple color while maintaining the darker shadows. The final code looks like this:

```html
    <section class="img-background">
      <img src="images/image-header-desktop.jpg" alt="" class="img-desktop"> 
    </section>  
```
```css
.img-background {
    background-color: hsl(280, 100%, 72%);
    border-radius: 0 10px 10px 0;
    display: flex;
}

.img-desktop {
    height: 100%;
    border-radius: 0 10px 10px 0;
    mix-blend-mode: multiply;
    filter: brightness(1) contrast(0.65)
}
```

### Continued development

In the future I would like to do a similar project and utilize CSS Grid instead of flexbox. I would also try a mobile-first approach as I started with the desktop version and worked back towards the mobile version with this project.

### Useful resources

- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) - This helped me as a general guide for flexbox.
- [Exploring Blend Modes in CSS](https://alligator.io/css/exploring-blend-modes) - As mentioned in the [What I learned](#what-i-learned) section, this resource helped me get close to the correct color levels on the card image.

## Author

- Github - [dan-dye](https://github.com/dan-dye)
- Frontend Mentor - [@dan-dye](https://www.frontendmentor.io/profile/dan-dye)

