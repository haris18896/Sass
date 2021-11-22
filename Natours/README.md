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

## Build Process
``` npm i concat --save-dev```

```
npm i autoprefixer --save-dev
npm i postcss-cli --save-dev
npm i postcss --save-dev
```

`autoprefixer` will add all the prefixes needed for the browsers.

```json
// package.json
  "scripts": {
    "watch-sass": "node-sass sass/main.scss css/styles.css -w",

    "compile-sass" : "node-sass sass/main.scss css/styles.comp.css",
    "concat-css": "concat -o css/styles.concat.css css/icon-font.css css/style.comp.css",
    "prefix-css": "postcss --use autoprefixer -b 'last 10 versions' css/styles.concat.css -o css/styles.prefix.css",
    "compress-css" : "node-sass css/styles.prefix.css css/styles.css --output-style compressed"
  },
```

at the end we will make a command to run all the `json commands` in the `package.json` file.

we made 2 .css files, one for the compiled css and one for the watching sass. so that when we make build we didn't want to compile the sass again.

* to run all the four commands `compile-sass, concat-css, prefix-css, compress-css` in a build we have to install an `npm package`

`npm install npm-run-all --save-dev`

```json
  "scripts": {
    "watch-sass": "node-sass sass/main.scss css/styles.css -w",

    "compile-sass": "node-sass sass/main.scss css/styles.comp.css",
    "concat-css": "concat -o css/styles.concat.css css/icon-font.css css/styles.comp.css",
    "prefix-css": "postcss --use autoprefixer -b 'last 5 versions' css/styles.concat.css -o css/styles.prefix.css",
    "compress-css" : "node-sass css/styles.prefix.css css/styles.css --output-style compressed",

    "build-css" : "npm-run-all compile-sass concat-css prefix-css compress-css"
  },
```

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
    8. make a build css file



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

```scss

    @media (min-resolution: 192dpi) and (min-width: 37.5em) , 
            (-webkit-min-device-pixel-ration: 2) and (min-width: 37.5em) ,          // for safari
            (min-width: 125em){
        background-image: 
        linear-gradient(
            to right bottom,
            rgba($color-secondary-light,0.8),
            rgba($color-secondary-dark,0.8),
            ),
        url('../img/hero.jpg');
    }
```

---
---

## Testing for browser support with `@supports`

```scss
.popup{
    height: 100vh;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba($color-black, 0.8);
    z-index: 9999;
    opacity: 0;
    visibility: hidden;
    transition:all .3s;
    -webkit-transition:all .3s;
    -moz-transition:all .3s;
    -ms-transition:all .3s;
    -o-transition:all .3s;


    @supports(-webkit-backdrop-filter: blur(10px)) or (backdrop-filter: blur(10px)){
        -webkit-backdrop-filter: blur(10px);
        backdrop-filter: blur(10px);
        background-color: rgba($color-black, 0.4);
    }
```

