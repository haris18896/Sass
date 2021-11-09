# Sass

## `Header`


```css
/*
COLORS:

Light green: #7ed56f
Medium green: #55c57a
Dark green: #28b485

*/

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body{
    font-family: 'Lato', sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.7;
    color: #777;
    padding: 30px;
}

.header{
    height: 95vh;
    background-image: 
        linear-gradient(
            to right bottom,
            #7ed56fb8,
            #28b485b8 ),
        url('../img/hero.jpg');
    background-size: cover;
    background-position: top;               /* top side always stays at the same top position*/
    clip-path: polygon(0 0,100% 0, 100% 75vh, 0% 100%);

}
```

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        
        <link href="https://fonts.googleapis.com/css?family=Lato:100,300,400,700,900" rel="stylesheet">

        <link rel="stylesheet" href="css/icon-font.css">
        <link rel="stylesheet" href="css/style.css">
        <link rel="shortcut icon" type="image/png" href="img/favicon.png">
        
        <title>Natours | Exciting tours for adventurous people</title>
    </head>
    <body>
        
        <header class="header">
            some text....
        </header>
        
    </body>
</html>
```

---
Now setting up the header elements. logo and navigation icon

    * when we specify the height of the <img> tag, then the width of the img tag will automatically be adjusted by the browser and vice versa

```css

.logo-box{
    position: absolute;
    top: 40px;
    left: 40px;
    
}

.logo{
    height: 35px;                       /* height of the logo */
}

.text-box{
    position: absolute;
    top: 40%;
    /*toppositionofthetextboxW.R.Tparentelement*/left: 50%;
    /*toppositionofthetextboxW.R.Tparentelement*//*background-color: red;
    */transform: translate(-50%, -50%);
    /*tocenterthetextbox*/-webkit-transform: translate(-50);
    -moz-transform: translate(-50%, -50%);
    -ms-transform: translate(-50%, -50%);
    -o-transform: translate(-50%, -50%);
    -webkit-transform: translate(-50%, -50%);
}

.heading-primary{
    color: #fff;
    text-transform: uppercase;
}

.heading-primary-main{
    display: block;
    font-size: 60px;
    font-weight: 400;
    letter-spacing: 35px;
}
.heading-primary-sub{
    display: block;
    font-size: 20px;
    font-weight: 400;
    letter-spacing: 17.4px;

}
```

```html
<header class="header">
    <div class="logo-box">
        <img src="./img/logo-white.png" alt="logo" class="logo" />
    </div>
    <div class="text-box">
        <h1 class="heading-primary">
            <span class="heading-primary-main">Outdoors</span>
            <span class="heading-primary-sub">is Where life happens</span>
        </h1>
    </div>
</header>
```
---

    * adding css animations and for that we will use `@key-frames`
```css
.heading-primary{
    color: #fff;
    text-transform: uppercase;
    backface-visibility: hidden;        /* hides the shaky animations, when animation is ended(it's a hack for the shaky animations) */
    -webkit-backface-visibility: hidden;
}

.heading-primary-main{
    display: block;
    font-size: 60px;
    font-weight: 400;
    letter-spacing: 35px;
    animation-name: moveInLeft;
    animation-duration: 1.5s;
    animation-timing-function: ease-out;


    /* animation-iteration-count: 3; */
    /*animation-delay: 3s;*/
}
.heading-primary-sub{
    display: block;
    font-size: 20px;
    font-weight: 400;
    letter-spacing: 17.4px;
    animation-name: moveInRight;
    animation-duration: 1.5s;
    animation-timing-function: ease-out;



    /* animation-delay: 3s; */
    /* animation-iteration-count: 3; */

}

@keyframes moveInLeft {
    0% {
        opacity: 0;
        transform: translateX(-100px);
        -webkit-transform: translateX(-100px);
        -moz-transform: translateX(-100px);
        -ms-transform: translateX(-100px);
        -o-transform: translateX(-100px);
}
    80%{
        transform: translateX(10px);
        -webkit-transform: translateX(10px);
        -moz-transform: translateX(10px);
        -ms-transform: translateX(10px);
        -o-transform: translateX(10px);
}
    100% {
        opacity: 1;
        transform: translateX(0);
        -webkit-transform: translateX(0);
        -moz-transform: translateX(0);
        -ms-transform: translateX(0);
        -o-transform: translateX(0);
}
}

@keyframes moveInRight {
    0% {
        opacity: 0;
        transform: translateX(100px);
        -webkit-transform: translateX(100px);
        -moz-transform: translateX(100px);
        -ms-transform: translateX(100px);
        -o-transform: translateX(100px);
}
    80%{
        transform: translateX(-10px);
        -webkit-transform: translateX(-10px);
        -moz-transform: translateX(-10px);
        -ms-transform: translateX(-10px);
        -o-transform: translateX(-10px);
}
    100% {
        opacity: 1;
        transform: translateX(0);
    }
}
```


    Steps:
    1. add a background image
    2. add a linear gradient to the background image
    3. add a `clip-path: polygon` to the the background image
    4. add logo the left side w.r.t to the parent element
    5. add text in the middle
    6. add css animation now.
    7. 

