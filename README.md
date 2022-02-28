responisve layout challenge 3

## Table of contents

- [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

### The challenge

tring to make your page close to the design image which is found in design folder.
or
you can see the design file in the figma by clicking this link:https://www.figma.com/file/dGPcL6Ym2avOt4736aHb2B/conquer-responsive-layout-week-1-final-challenge?node-id=1%3A2

### Screenshot

![](./screenshot.jpg)
file path for the screenshot of my solution:
solution image/responsive design layout challenge-3.png


### Links

- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

I start with HTML 5 where I added a div class of main content with 3 child elements (h1 for heading , p for the paragraph and a for a link) to make the upper section which have a background colour of black thing as shown above in the design folder.

```
HTML
 <div class="main-content">
          <h1 class="responsive"> Responsive layouts don’t have to be a
            struggle</h1>

          <p class="description">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
            ut labore et dolore magna aliqua. Ut enim ad minim veniam.</p>

          <a href="#" class="main-btn"> I want to learn </a>
 </div>
```

second I create variables inorder to store the values of the property which i need for the elements in the page such as colors, font-size,font-weight.

```
css
:root {
  /*responsive */
  --background-black: hsla(192, 36%, 21%, 1);
  --roboto: "Roboto", sans-serif;
  --font-weight-900: 900;
  --font-size-48: 3.003rem;
  --line-height-56: 3.5rem;
  --white: #ffffff;
  /* description */
  --line-height-34: 1.971rem;
  /*button-section */
  --background-cyan: #38cfd9;
  --text-color: hsla(184, 73%, 10%, 1);
  --border-radius: 35px;
  --letter-spacing: 0.05em;
  --uppercase: uppercase;
  --font-weight-bold: bold;
  --font-size-21: 1.312rem;
  --line-height-150: 150.19%;
  --left-padding: 3.06rem;
}
```

then I style the responsive, description , main-btn according to the style given in the figma file 
but when I add the margin and padding to the main-btn it's margin-top and the padding-top of the element doen't change. it is because the main-btn is a" link" and links are  inline element so 
margin-top .padding-top,margin-bottom, padding-bottom,width and height doesn't change the look of the element in the page even if you apply the value for it in your css. so I change the display: inline(which is the default value for the inline elements) to display: inline-block; inorder to make margin-top and padding-top properties work  .

```
css
.responsive {
  font-weight: var(--font-weight-900);
  color: var(--white);
  font-size: var(--font-size-48);
  line-height: var(--line-height-56);
}


.description {
  color: gray;
  line-height: var(--line-height-34);
  margin: 1.2rem 0;
  font-size: 1.3125rem;
  font-weight: 300;
}


.main-btn {
  display: inline-block;
  background: var(--background-cyan);
  line-height: var(--line-height-150);
  color: var(--text-color);
  text-decoration: none;
  border-radius: 35px;
  letter-spacing: 0.05em;
  text-transform: var(--uppercase);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-21);
  padding: 1rem var(--left-padding);
  margin: 1.7rem 0 0;
  text-align: center;
}

```

then I styled the main-content with a max-width inorder to limith the width of it's child elements so they will have a limited width they will look the same as a design .

```
css
.main-content{
  max-width: 710px;
}
```

I add the margin of 1.625rem to the top and the bottom inorder to add space at the top and bottom of the main-content add a margin of auto to the left and the right to center it inside the body.

```
css
.main-content{
  max-width: 710px;
  margin: 1.625rem auto;
}
```

the main-content willnot have space at left and right when the screen gets smaller because of it's default width of 100%.
so, we should add a width of 90% to the main-content. so it will have space at the left and right and also it will be responsive.

```
css
.main-content{
  max-width: 710px;
  margin: 1.625rem auto;
  width: 90%;
}
```

I wrap the main-content class with a div class of the container inorder to add the background color which extends from one side of the the viewport to the other. since width of the main-content is limited with a max-width and width property if I add the background to it won't extend from one side of the view port to the other.

```
HTML
<div class="container">
      <div class="main-content">
          <h1 class="responsive"> Responsive layouts don’t have to be a
            struggle</h1>

          <p class="description">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
            ut labore et dolore magna aliqua. Ut enim ad minim veniam.</p>

          <a href="#" class="main-btn"> I want to learn </a>
      </div>

  </div>
```

```
css
.container{
  background: var(--background-black);
}
```

I add padding top and bottom to container class to add more space at the top and bottom of the main-content. it will make them to look the same as the design.

```
css
.container{
  background: var(--background-black);
  padding: 7.625rem 0;
}
```

finally, the page will look like the one which is in a design
but the text will big when the screen size get's smaller so i should decrease the font-size ,padding and others. since all of the sizes I have given to the width , margin and other are
in a rem . we can decrease the font-size for the html document and all the sizes of the element in the markup will be decreased.

```
css
@media screen and (max-width: 500px) {
  html {
    font-size: 10px;
  }

  .container {
    padding: 5rem 0;
  }

  .main-content {
    min-height: 350px;
    /*I  give min-height to the main-content inorder to increase the size of the main-content this will extend the background-color to the bottom which we have given the container class. */
  }
}
```

### Built with

- Semantic HTML5 markup
- CSS 3

### What I learned

in this section I learn about that width and height doesn't affect inline elements such as a link .

### Continued development

i want to focus on responsive design,flexbox , grid.

## Author

- frontendmentor - [@aemrobe](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@Aemro112](https://www.twitter.com/yourusername)
- freecodecamp - [@aemro11]
