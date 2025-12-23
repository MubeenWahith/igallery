# Ex.07 Design of Interactive Image Gallery
## Date:

## AIM:
To design a web application for an inteactive image gallery for a minimum five images with next and previous buttons.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM:
```
imahome.html

<html>
<head>
    
    <title>Creative Gallery</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

<h2>Interactive Football Gallery</h2>
<h3>MOHAMED MUBEEN.A (25004201)</h3>
<hr>
<br>
<br>

<div class="gallery">
    <img src="1.jpeg" data-title="Cristiano Ronaldo" onclick="openImage(this)">
    <img src="2.jpeg" data-title="Leo Messi" onclick="openImage(this)">
    <img src="3.avif" data-title="Sergio Ramos" onclick="openImage(this)">
    <img src="4.jpg" data-title="Toni Kross" onclick="openImage(this)">
    <img src="5.jpeg" data-title="Kylian Mbappe" onclick="openImage(this)">
    <img src="6.jpg" data-title="Zinedine Zidane" onclick="openImage(this)">
    <img src="7.avif" data-title="Marco van Basten" onclick="openImage(this)">
    <img src="8.webp" data-title="David Beckham" onclick="openImage(this)">
    <img src="9.jpeg" data-title="Marco van Basten" onclick="openImage(this)">
    <img src="10.webp" data-title="paolo maldini" onclick="openImage(this)">
</div>
<br>
<br>
<hr>

<div class="modal" id="imageModal" onclick="closeImage()">
    <div class="modal-content" onclick="event.stopPropagation()">
        <span class="close" onclick="closeImage()">&times;</span>

        
        <img id="modalImg" src="">

        <p id="caption"></p>
    </div>
</div>

<script src="script.js"></script>
</body>
</html>

```
```
style.css

body {
    font-family: "Segoe UI", sans-serif;
    margin: 0;
    padding: 40px;
    color: white;

    background-image: url("bg.jpg");
    background-position: center;
    background-repeat: no-repeat;
    background-size: contain;
    background-size: cover;
}


h2 {
    text-align: center;
    margin-bottom: 30px;
    letter-spacing: 2px;
}
h3{
    text-align: center;
    margin-bottom: 30px;
    letter-spacing: 2px;
}


.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 30px;
    max-width: 1000px;
    margin: auto;
}

.gallery img {
    width: 100%;
    height: 220px;
    object-fit: cover;
    border-radius: 12px;
    cursor: pointer;
    transition: transform 0.4s, box-shadow 0.4s;
}

.gallery img:hover {
    transform: scale(1.08);
    box-shadow: 0 20px 40px rgba(0,0,0,0.5);
}


.modal {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.8);
    backdrop-filter: blur(6px);
    justify-content: center;
    align-items: center;
    animation: fadeIn 0.4s;
}

.modal-content {
    background: #111;
    padding: 20px;
    border-radius: 16px;
    text-align: center;
    animation: zoomIn 0.4s;
}

.modal img {
    max-width: 80vw;
    max-height: 70vh;
    border-radius: 12px;
}

#caption {
    margin-top: 12px;
    font-size: 18px;
    color: #ddd;
}

.close {
    position: absolute;
    top: 20px;
    right: 30px;
    font-size: 32px;
    cursor: pointer;
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

@keyframes zoomIn {
    from { transform: scale(0.7); }
    to { transform: scale(1); }
}
@keyframes gradientBG {
    0%   { background-position: 0% 50%; }
    50%  { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}


```
```
script.js

function openImage(img) {
    const modal = document.getElementById("imageModal");
    const modalImg = document.getElementById("modalImg");
    const caption = document.getElementById("caption");

    modal.style.display = "flex";
    modalImg.src = img.src;       
    caption.innerText = img.dataset.title || "";
}

function closeImage() {
    document.getElementById("imageModal").style.display = "none";
}

```

## OUTPUT:
![alt text](<Screenshot (52).png>)

![alt text](<Screenshot (53).png>)
## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
