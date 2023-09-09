# Day15Assignment
## Hosted Link:
https://praveshjangid2001.github.io/Day15Assignment/
## html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Day15Assignment</title>
    <link rel="stylesheet" href="./style.css">
</head>
<body>
    <div class="container">
        <h3>Anime Pics Generator</h1>
        <button class="btn" id="btn">Get Anime</button>
        <div class="anime-container">
            <img class="anime-img" src="https://c.files.bbci.co.uk/F382/production/_123883326_852a3a31-69d7-4849-81c7-8087bf630251.jpg">
            <h3 class="anime-name">Anime Name</h3>
        </div>
    </div>
    <script src="./index.js"></script>
</body>
</html>
```
## css
```css
const btnEl = document.getElementById("btn");
const animeContainerEl = document.querySelector(".anime-container");
const animeImgEl = document.querySelector(".anime-img");
const amineNameEl = document.querySelector(".anime-name");

btnEl.addEventListener("click", async function () {
  try {
    btnEl.disabled = true;
    btnEl.innerText = "Loading...";
    amineNameEl.innerText = "Updating...";
    animeImgEl.src = "spinner.svg";
    const response = await fetch("https://api.catboys.com/img");
    const data = await response.json();
    btnEl.disabled = false;
    btnEl.innerText = "Get Anime";
    animeContainerEl.style.display = "block";
    animeImgEl.src = data.url;
    amineNameEl.innerText = data.artist;
  } catch (error) {
    console.log(error);
    btnEl.disabled = false;
    btnEl.innerText = "Get Anime";
    amineNameEl.innerText = "An error happened, please try again";
  }
});
```
## js
```js
body {
    display: flex;
    height: 100vh;
    justify-content: center;
    align-items: center;
    font-family: "Courier New", Courier, monospace;
    margin: 0px;
    background: linear-gradient(to right, lightblue, yellow);
}
.container {
    box-shadow: rgba(0, 0, 0, 0.3) 0px 10px 20px;
    text-align: center;
    width: 450px;
    background: aliceblue;
    border-radius: 10px;
    padding: 10px;
    margin: 5px;
}
div {
    display: block;
}
h3 {
    display: block;
    font-size: 1.17em;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}
.btn {
    background-color: green;
    color: aliceblue;
    font-size: 16px;
    margin-bottom: 30px;
    cursor: pointer;
    padding: 10px 30px;
    border-radius: 6px;
}
.anime-container {
    display: none;
}
.anime-img {
    height: 300px;
    width: 300px;
    border-radius: 50%;
    border-width: 3px;
    border-style: solid;
    border-color: green;
    border-image: initial;
}
img {
    overflow-clip-margin: content-box;
    overflow: clip;
}
.anime-name {
    background-color: green;
    color: aliceblue;
    font-size: 17px;
    font-weight: 600;
    margin: 20px;
    padding: 10px;
    border-radius: 6px;
}
```


```
