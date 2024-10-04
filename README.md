
# DAY_003 | Photo Gallery

This project is part of the daily code challenge series, **DAY_003**, and it demonstrates a simple Photo Gallery with expanding images when you click on them. The gallery is built using HTML, CSS, and JavaScript, and it uses animated `.gif` images.

## Project Structure

```bash
DAY_003/
│
├── images/
│   ├── 1.gif
│   ├── 2.gif
│   ├── 3.gif
│   ├── 4.gif
│   ├── 5.gif
│   ├── 6.gif
│   └── logo1.png  
├── index.html
├── app.js
├── style.css
├── IvarDisplayCondensed-Light.woff2
└── NeueMontreal-Light.woff
```

## Features

- **Grid Layout**: Images are arranged in a grid, and when you click on one, it expands.
- **GIF Animations**: The gallery uses animated `.gif` images as the background for each item.
- **Custom Fonts**: Two special fonts are used for styling: `IvarDisplayCondensed-Light` and `NeueMontreal-Light`.
- **Logo**: Includes `logo1.png` displayed in the header.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/thounny/DAY_003.git
   ```
2. Open the `index.html` file in your web browser.

## How the JavaScript Works

### Adding Images to Each Grid Item

The JavaScript automatically adds images to each item in the grid by going through them one by one:

```javascript
const images = document.querySelectorAll('.img');

images.forEach((img, idx) => {
  img.style.backgroundImage = `url(./images/${idx + 1}.gif)`; // Add .gif images
});
```
This loop makes sure that each grid item gets a `.gif` image from the `images/` folder.

### Clicking on a Grid Item

When you click on a grid item, it expands and highlights the image. If you click again, it resets:

```javascript
const gridItems = document.querySelectorAll('.grid-item');

gridItems.forEach((item, idx) => {
  item.addEventListener("click", (e) => {
    // Remove active class from all items
    gridItems.forEach(item => item.classList.remove("active"));

    // Check if the clicked item is already active
    if (!e.target.classList.contains("active")) {
      item.classList.add("active"); // Add active class to clicked item
    } else {
      resetGrid(); // Reset grid if clicked again
    }
  });
});
```

This code checks if a grid item is already active (clicked). If it is not, it adds an "active" class to expand it. If it is active, it resets the layout.

### Resetting the Layout

If an image is clicked again, the grid resets to its original form:

```javascript
function resetGrid() {
  gridItems.forEach(item => item.classList.remove("expand"));
}
```

This function removes the "expand" effect from all grid items when called.

---

## Author

![logo](https://web.archive.org/web/20091027053343/http://geocities.com/animecap/index_dwn.gif)

**Thounny Keo**  
Frontend Development Student | Year Up United