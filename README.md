# advance-css
Advance CSS concepts.


## Targeted Selector

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

![Targed Selector](img/1_targeted_selector.png)


## nth-child Selector

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

![Targed Selector](img/2_nth-child.png)