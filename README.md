# Ex05 Image Carousel
## Date: 27.05.2026
## Name: K DHANUSRI POOJA

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM

APP.JSX

```
import "./App.css";
import { useState } from "react";

function App(){

  const images = [

    "https://via.placeholder.com/300",

    "https://via.placeholder.com/300/ff0000",

    "https://via.placeholder.com/300/0000ff"

  ];

  const [index, setIndex] = useState(0);

  function nextImage(){

    if(index === images.length - 1){

      setIndex(0);

    }else{

      setIndex(index + 1);
    }
  }

  function prevImage(){

    if(index === 0){

      setIndex(images.length - 1);

    }else{

      setIndex(index - 1);
    }
  }

  return(

    <div className="box">

      <h1>Image Carousel</h1>

      <img src={images[index]} />

      <br /><br />

      <button onClick={prevImage}>
        Previous
      </button>

      <button onClick={nextImage}>
        Next
      </button>

    </div>
  );
}

export default App;
```

APP.CSS

```
body{
  font-family: Arial;
  background: #f0f0f0;
  text-align: center;
}

.box{
  background: white;
  width: 350px;
  padding: 20px;
  margin: auto;
  margin-top: 50px;
}

img{
  width: 300px;
}

button{
  padding: 10px;
  margin: 5px;
  background: black;
  color: white;
  border: none;
}
```



## OUTPUT
<img width="1230" height="673" alt="image" src="https://github.com/user-attachments/assets/ca338d24-5eb6-4550-b438-c3a71321b7e2" />
<img width="1238" height="654" alt="image" src="https://github.com/user-attachments/assets/45874ca5-514e-4139-a1e1-5c1e196e327a" />


## RESULT
The program for creating Image Carousel using React is executed successfully.
