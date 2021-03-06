# advance-css
Advance CSS concepts.

## Table of Contents

* [Targeted Selector](#Targeted-Selector)
* [nth-child Selector](#nth-child-Selector)
* [Before & After Pseudo Class](#Before-&-After-Pseudo-Class)
* [Box Shadow](#Box-Shadow)
* [Text Shadow](#Text-Shadow)
* [CSS Variables](#CSS-Variables)
* [Keyframe Animation](#Keyframe-Animation)
* [Transitions](#Transitions)

---

## Targeted Selector

##### [Table of Contents](#Table-of-Contents)

By using targetted type of selector, we can select specifi elements by relationship, such as Direct Child ` > `, Directly After ` + `, By Atttribute ` [ ] `, Specific Attribute values ` ='' `. 


```css
/* Direct child */
div > p {
    background: #ddd;
}

/* Directly after */
div + p {
    background: #333;
    color: #fff;
}

/* By attribte */
a[target] {
    background: #ff0000;
    color: #fff;
}

/* Specific attribute values */
input[type="text"], input[type="email"] {
    width: 100%;
    margin-bottom: 5px;
}
```

![Targeted Selector](img/1_targeted_selector.png)

---

## nth-child Selector

##### [Table of Contents](#Table-of-Contents)

The nth-child selctor allows us to select the child elements of the parents. It is a pseudo selector such as `:first` and `:last` to directly select from parents, but use the `nth-child()` method when select specific child elements. 

```css
li {
    padding: 0.25rem;
    margin: 0.25rem;
    list-style: none;
}

/* first-child */
li:first-child {
    background: red;
}

/* last-child */
li:last-child {
    background: red;
}

/* Position 3 */
li:nth-child(3) {
    background: purple;
}

/* Every 3rd one */
li:nth-child(3n+0) {
    background: orange;
}

/* Every 3 afer 7 */
li:nth-child(3n+7) {
    background: yellow;
}

/* Every odd */
li:nth-child(odd) {
    background: #ccc;
}

/* Every even */
li:nth-child(even) {
    background: #ddd;
}
```

![nth-child Selector](img/2_nth-child.png)

---

## Before & After Pseudo Class

##### [Table of Contents](#Table-of-Contents)

The `:after` selector is a **pseudo-class** that allows you to add content **after** selected element. This element is an inline elmenet.  The `:before` does the opposite.

```css
body {
    font-family: Arial, Helvetica, sans-serif;
    background: #333;
    color: #fff;
    margin: 0;
}

header {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    height: 100vh;
}

header:before {
    content: '';
    background: url('https://source.unsplash.com/weekly?water') no-repeat center center/cover;
    opacity: 0.3;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
}

header > h1 {
    font-size: 4rem;
    margin: 1rem;
}

.is-required:after {
    content: '*';
    color: red;
    padding-left: 2px;
}
```

![before-after](img/3_before-after.png)

---

## Box Shadow

##### [Table of Contents](#Table-of-Contents)

Box shadow properties allows us to add shadows on our elements.

```css
.container {
    display: flex;
}

.box {
    padding: 1rem;
    margin: 1rem;
    background: coral;
    color: #fff;

    /* offset-x | offset-y | color */
    box-shadow: 10px 10px teal;

    /* offset-x | offset-y | blur-radius | color */
    box-shadow: 5px 5px 20px teal;

    /* Negative values */
    box-shadow: -5px -5px 20px teal;

    /* offset-x | offset-y | blur-radius | spread-radius | color */
    box-shadow: 3px 3px 10px 1px rgba(0, 0, 0, 0.3);

    /* inset | offset-x | offset-y | color */
    box-shadow: inset 3px 3px teal;

    /* Multiple Shadows */
    box-shadow: 3px 3px 10px teal, -3px -3px 10px olive;
}
```

![box-shadow](img/4_box-shadow.png)

---

## Text Shadow

##### [Table of Contents](#Table-of-Contents)

Test shadow properties allows us to add shadows on our text.

```css
h1 {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 4rem;
}

h1.a {
    /* h-shadow | v-shadow | color */
    text-shadow: 0.2rem 0.2rem steelblue;
}

h1.b {
    /* h-shadow | v-shadow | blue | color */
    text-shadow: 0.4rem 03rem 0.7rem steelblue;
}

h1.c {
    /* White Text */
    color: #fff;
    text-shadow: 0.2rem 0.2rem 1rem steelblue;
}

h1.d {
    /* Negative Value */
    text-shadow: -0.4rem -0.3rem 0.7rem steelblue;
}
```

![text-shadow](img/5_text-shadow.png)

---

## CSS Variables

##### [Table of Contents](#Table-of-Contents)

CSS Variables allows us to store values that can later be used in other parts of our styling. This reduces the need to have duplicate properties.
Use the `--` to declare a variable, and `var(-- )` to call the variable.

```css
:root {
    --max-width: 960px;
    --primary-color: steelblue;
    --secondary-color: skyblue;
    --light-color: #f4f4f4;
    
}

.box {
    --box-1-width: 1;
    --box-2-width: 2;
}

    /* Add a Reset */
    * {
        margin: 0;
        padding: 0;
    }

    body {
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1.4;
        background: var(--light-color);
    }

    header {
        background-color: var(--primary-color);
        border-bottom: 5px var(--secondary-color) solid;
        color: #fff;
        text-align: center;
    }

    .container {
        display: flex;
        margin: auto;
        max-width: var(--max-width);
    }

    .box {
        background-color: var(--primary-color);
        border-bottom: 5px var(--secondary-color) solid;
        color: #fff;
        padding: 1rem;
        margin: 1rem;
    }

    .box-1 {
        flex: var(--box-1-width);
    }

    .box-2 {
        flex: var(--box-2-width);
    }
```

![css-variables](img/6_css-variables.png)

---

## Keyframe Animation

##### [Table of Contents](#Table-of-Contents)

We can use the attribute `animation` to handles the various different CSS properties, along with the `@keyframes` method to handle the request.

```css
body {
    background: #333;
}

.box {
    background: white;
    width: 200px;
    height: 200px;
    position: relative;
    /* animation-name: animate1;
    animation-duration: 5s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
    animation-delay: 2s;
    animation-direction: alternate;
    animation-timing-function: ease-in-out; */
    animation: animate1 5s forwards 1s ease-in-out;
}

@keyframes animate1 {
    from {
        top: 0;
    }

    to {
        width: 600px;
        background-color: red;
        top: 300px;
    }
}
```

![keyframe-1](img/7_keyframe-animation.gif)

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Keyframes 2</title>
    <style>
        body {
            background: #333;
        }

        .box {
            background: #fff;
            width: 200px;
            height: 200px;
            position: relative;
            top: 0;
            left: 0;
            animation: animate1 5s forwards ease-in-out;
        }

        @keyframes animate1 {
            25% {
                top: 0;
                left: 300px;
                background: red;
                border-radius: 50% 0 0 0;
            }

            50% {
                top: 300px;
                left: 300px;
                background: green;
                border-radius: 50% 50% 0 0;
            }

            75% {
                top: 300px;
                left: 0;
                background: blue;
                border-radius: 50% 50% 50% 0;
            }

            100% {
                top: 0;
                left: 0;
                background: white;
                border-radius: 50% 50% 50% 50%;
            }
        }
        
    </style>
</head>
<body>
    <div class="box">

    </div>
    
</body>
</html>
```

![keyframe-2](img/8_keyframe-animation-2.gif)

## Transitions

##### [Table of Contents](#Table-of-Contents)

We can use the attribute `transition` to changes, use with the `pseudo class` properties.

```css
body {
    background: #333;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
}

.box {
    background: white;
    width: 100px;
    height: 100px;
    /* transition-property: background;
    transition-duration: 2s;
    transition-timing-function: ease-in-out; */
    /* transition-delay: 3s; */
    transition: all 2s ease-in-out;
}

.box:hover {
    background: red;
    border-radius: 50%;
    height: 300px;
    width: 300px;
}
```

![transitions](img/9_transitions.gif)
