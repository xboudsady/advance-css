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