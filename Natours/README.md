# Sass
```
npm init
npm install node-sass --save dev

```

compile the `Scss` to `css` using `node-sass`

for that we will have to write a `script` in the `package.json` file, iin this file will add the input and output of the sass directories.
the `-w` flag means the sass is watching for the changes.

   `"compile-sass": "node-sass sass/main.scss css/styles.css -w"`

   `npm run compile-sass`

---
---

## `adding live server`
`npm install live-server --save-dev`

but we are going to install it globally
`npm i -g live-server`

`$ live-server`

---
---

    Header:
    
    1. add a background image
    2. add a linear gradient to the background image
    3. add a `clip-path: polygon` to the the background image
    4. add logo the left side w.r.t to the parent element
    5. add text in the middle
    6. add css animation now.
    7. adding an animated anchor button



## Responsive Images in HTML

```html
 <!-- -->
 <!-- # Resolution Switching-->
 <!-- the below method will take care of both Resolution switching and Density Switching  -->
 <img
     srcset="img/nat-1.jpg 300w, img/nat-1-large.jpg 1000w"
     sizes="(max-width: 900px) 20vw (max-width: 600px) 30vw, 300px"
     alt="photo-1"
     class="composition__photo composition__photo--p1"
     src="img/nat-1-large.jpg"
     />
<!-- -->




<!-- -->    
 <!-- # Density Switching -->
 <!-- <img srcset="img/logo-green-1x.png 1x, img/logo-green-2x.png 2x" alt="logo" class="footer__logo" /> -->
 <!-- -->

 <!-- -->    
 <!-- # Art Diirections -->
 <!-- uploading different images for different screen width -->
 <picture class="footer__logo">
     <source srcset="img/logo-green-small-1x.png 1x, img/logo-green-small-2x.png 2x"
             media="(max-width: 37.5em)"
             src="img/logo-green-2x.png">
     <img 
         srcset="img/logo-green-1x.png 1x, img/logo-green-2x.png 2x"
         alt="logo"
         class="footer__logo"
         src="img/logo-green-2x.png"
      /> 

 </picture>
 <!-- --> 
```
---
---


## Responsive Images in CSS

for that we will use `@media query`, 

```scss

.header{
    background-image: 
        linear-gradient(
            to right bottom,
            $color-primary-light,
            $color-primary-dark,
            ),
        url('../img/hero-small.jpg');

    // .........
    // .........

    @media (min-resolution: 192dpi){
        background-image: 
        linear-gradient(
            to right bottom,
            $color-primary-light,
            $color-primary-dark,
            ),
        url('../img/hero.jpg');
    }
```


```scss
    @media (min-resolution: 192dpi) and (min-width: 600px){
        background-image: 
        linear-gradient(
            to right bottom,
            rgba($color-secondary-light,0.8),
            rgba($color-secondary-dark,0.8),
            ),
        url('../img/hero.jpg');
```

```scss
    // change the 600px and 2000px to '37.5em and 125em' respectively.
    @media (min-resolution: 192dpi) and (min-width: 600px) , 
            (min-width: 2000px){
        background-image: 
        linear-gradient(
            to right bottom,
            rgba($color-secondary-light,0.8),
            rgba($color-secondary-dark,0.8),
            ),
        url('../img/hero.jpg');
    }
```

