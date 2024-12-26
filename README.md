# Ex.08 Design of Interactive Image Gallery
## Date:25.12.2024

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

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

## PROGRAM :
'''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Gallery</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #f06, #4a90e2);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        h1 {
            font-size: 3em;
            color:black;
            font-weight: bold;
            margin-bottom: 20px;
            animation: fadeIn 3s ease-in-out;
        }

        @keyframes fadeIn {
            0% {
                opacity: 0;
                transform: translateY(-20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-gap: 15px;
            width: 80%;
            max-width: 800px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 20px;
            cursor: pointer;
            transition: transform 0.3s ease;
            height: 200px; /* Adjusted height */
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease, filter 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
            filter: brightness(0.8);
        } .overlay { 
            position: absolute; 
            top: 0; 
            left: 0; 
            width: 100%; 
            height: 100%; 
            background-color: rgba(0, 0, 0, 0.5); 
            color: white; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            opacity: 0; 
            transition: opacity 0.3s ease; 
        } 
        .gallery-item:hover .overlay { 
            opacity: 1;
         } 
         .full-screen { 
            position: fixed; 
            top: 50%; 
            left: 50%; 
            transform: translate(-50%, -50%); 
            width: 90%; height: 90%; 
            background-color: rgba(0, 0, 0, 0.9); 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            z-index: 10; 
            opacity: 0; 
            visibility: hidden; 
            transition: opacity 0.3s ease, visibility 0.3s ease; 
        } 
        .full-screen img 
        {
             width: 100%; 
            height: 100%; 
            object-fit: contain; 
            border-radius: 20px;
         } .full-screen.active 
         { 
            opacity: 1; 
            visibility: visible; 
        } 
        .close-btn 
        { 
          position: absolute; 
          top: 20px; 
          right: 20px; 
          font-size: 2em; 
          color: white; 
          cursor: pointer; 
          background: none;
        }
    </style>
</head>
<body>
    <h1>Image Gallery</h1>
    <div class="gallery" id="gallery"></div>

    <div class="full-screen" id="fullScreen">
        <button class="close-btn" id="closeBtn">&times;</button>
        <img id="fullScreenImg" src="" alt="Full View">
    </div>

    <script>
        const gallery = document.getElementById('gallery');
        const fullScreen = document.getElementById('fullScreen');
        const fullScreenImg = document.getElementById('fullScreenImg');
        const closeBtn = document.getElementById('closeBtn');

        const images = [
            'ig1.jpg',
            'ig2.png',
            'ig3.jpg',
            'ig4.jpg',
            'ig5.jpg',
            'ig6.jpg',
            'ig7.jpg',
            'ig8.jpg',
            'ig9.jpg',
            
        ];

        images.forEach((src, index) => {
            const item = document.createElement('div');
            item.classList.add('gallery-item');

            const img = document.createElement('img');
            img.src = src;
            img.alt = `Image ${index + 1}`;

            const overlay = document.createElement('div');
            overlay.classList.add('overlay');
            overlay.innerText = `Image ${index + 1}`;

            item.appendChild(img);
            item.appendChild(overlay);
            gallery.appendChild(item);

            item.addEventListener('click', () => {
                fullScreenImg.src = src;
                fullScreen.classList.add('active');
            });
        });

        closeBtn.addEventListener('click', () => {
            fullScreen.classList.remove('active');
        });

        fullScreen.addEventListener('click', (e) => {
            if (e.target === fullScreen || e.target === closeBtn) {
                fullScreen.classList.remove('active');
            }
        });
    </script>
</body>
</html>

'''

## OUTPUT:
![alt text](<Screenshot 202.png>)
![alt text](<Screenshot 2024-12-26 142608.png>)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
