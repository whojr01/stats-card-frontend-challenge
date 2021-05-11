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
- [Author](#author)
- [Acknowledgments](#acknowledgments)


## Overview
The code in this repository was created from frontendmentor.com so it is not part of a bigger project. Please feel free to use any parts of it should you find it of value.

If your looking for a good challenge check out frontendmentor.com they have a ton of really good challenges.

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size

### Screenshot


![](./Screenshot_Stats_preview_card.png)

Above is what you should see when you click on the link below.

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process
- Study the requirements and provided Screenshots
- Define the HTML structure
- Define the CSS custom properties
- Test on the Blisk browser for IOS, iPhone, Android, and desktop
  - Cleanse, rinse, and redo (LOL more than a few times ;-)
### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

I learned a lot about the subtle differences between images and background-images and how they impact the layout. I never worked with linear gradients layered on top of images which turned out to be a real eye opener.

My first strategy was to use a background image and I couldn't control the width of the div as the design specification dictated. To solve the problem I used the ::after selector to create a psudeo element in order to get the linear gradient positioned properly (see below). 

I used the img srcset attribute to make the images responsive in a div.

```html
  <div class="filt">
      <img src="./images/image-header-mobile-375.jpg"
      alt="Women sitting at tables facing each other while working on computers"
      srcset="./images/image-header-mobile-375.jpg 375w,
      ./images/image-header-desktop.jpg 654w"
      sizes="(max-width: 375px) 375px, 654px">
  </div>
```
Then I made the div relative in order to create a new flow which allowed me to make the ::after an absolute to position the linear gradient.

```css
.filt {
  position: relative;
}

.filt::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(to bottom right,hsl(278, 42%, 36%, .8),hsl(278, 42%, 36%, .8));
  opacity: 0.75;
}
```

## Author

- Website - [William Oliver](https://www.whojr.com)
- Frontend Mentor - [William Oliver](https://www.frontendmentor.io/profile/whojr01)


## Acknowledgments

Thanks to Kevin Powell (Youtube CSS - I love his channel). Kevin is dedicated to teaching CSS and he is an awesome teacher, so check him out! [Kevin Powell](https://www.youtube.com/channel/UCJZv4d5rbIKd4QHMPkcABCw).
