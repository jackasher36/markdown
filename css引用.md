偶然发现一个不错的css代码引用

```css
/* styles.css */

body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 0;
    padding: 0;
    background-color: #f9f9f9;
}

h1 {
    margin-top: 20px;
    color: #333;
}

form {
    margin: 0 auto;
    max-width: 400px;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 5px;
    background-color: #f9f9f9;
}

label {
    display: block;
    margin-bottom: 10px;
    text-align: left;
}

input[type="text"] {
    width: calc(100% - 20px);
    padding: 8px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
}

input[type="submit"] {
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

input[type="submit"]:hover {
    background-color: #0056b3;
}

```



调用时使用

```html
<link rel="stylesheet" type="text/css" href="styles.css">

```

