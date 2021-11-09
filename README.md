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






    Steps:
    1. add a background image
    2. add a linear gradient to the background image
    3. add a `clip-path: polygon` to the the background image

