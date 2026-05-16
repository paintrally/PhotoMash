# PhotoMash

A simple, web-based image editor built by stitching together awesome open-source snippets and web tutorials. This is my very first Macando / Hack Club project! I wanted to see if I could take different pieces of code from around the internet, mix them together, and build a unique tool that actually works.

---

## Features

* **Quick Adjustments:** Sliders to tweak Brightness, Contrast, and Saturation on the fly.
* **Transformations:** Tools to rotate up to 360°, scale, or flip your image vertically and horizontally.
* **Canvas Cropping:** Click "Start Crop" to free-hand draw a box over your photo, then hit "Apply Crop" to chop out the rest.
* **100% Local:** Runs entirely inside your browser. No servers, no accounts, and no tracking.
* **Weird Background:** Uses a layered CSS gradient blend-mode trick to create a vibrant, retro backdrop.

---

## The Bugs I Fixed (Why it was a bit tricky)

Splicing code isn't just copying and pasting—things break! Here are a few things I had to fix to get the code snippets to talk to each other:

1. **ID Mismatches:** The HTML file used `id="cropBtn"` and `id="applyBtn"`, but the JavaScript snippet was looking for `crop-btn` and `apply-crop-btn`. The buttons did absolutely nothing until I matched up the IDs.
2. **Broken Flip Logic:** The `flipHorizontal` and `flipVertical` event listeners in the JavaScript were trying to target `flip-horizontal` and `flip-vertical`, which didn't exist in the HTML. I mapped them back to the right buttons so the image actually flips now.
3. **Canvas Redrawing:** Balancing the sliders with the transformation canvas required making sure `applyEdits()` and `drawImage()` didn't constantly override each other's parameters. 

---

## How I Built This (My Process)

Since this was my first Hack Club project, I started with a blank page and a lot of tabs open. 

First, I found a vanilla JavaScript image editor tutorial that handled the basic canvas logic. But the interface was pretty plain, so I started looking for ways to make it look unique. I found a cool CodePen that used complex CSS radial gradients and blend modes to make a shifting, trippy background, and I decided to splice that into the body of the page.

From there, it was a game of whack-a-mole with the layout. I used basic HTML `<center>` tags and the `<mark>` tag to quickly lay out the controls without getting completely bogged down in custom flexbox grid styling for hours. The hardest part was getting the buttons to actually fire their functions, because when you grab HTML from one source and JavaScript from another, names rarely match up perfectly. 

---

## How to Run It Locally

If you want to run this project on your own machine, follow these steps:

1. Clone this repository or download the ZIP file containing `index.html` and `editor.html`.
2. Make sure both files are saved in the exact same folder so the links don't break.
3. Double-click `index.html` to launch the home page in any modern web browser (Chrome, Firefox, Safari, Edge, etc.).
4. Click the big **"Go to PhotoMash"** button.
5. Hit the "Choose File" upload button at the top, select any image from your computer, and start messing with the sliders!

---

## Future Ideas & Wishlist

I'm definitely not done learning, and I'd love to expand this project as I get better at JavaScript:
* **Add Retro Presets:** Buttons that let you instantly turn an image black-and-white, sepia, or completely inverted.
* **Text Overlays:** A text input box so you can add funny captions or text memes directly onto the canvas before downloading.
* **An Undo Button:** Right now, if you mess up a crop, you have to re-upload the image. I want to add a state history so users can step backward if they make a mistake.

---

## Thanks and Attributions

This project is a Frankenstein monster of great code bits found across the web. Big thanks to these creators:

* [Advanced Image Editor with Vanilla JavaScript (GitHub)](https://github.com/codehuntersharath/Advanced-Image-Editor-with-Vanilla-JavaScript/tree/main) & [Dev.to Tutorial](https://dev.to/codehuntersharath/build-an-advanced-image-editor-with-html-css-javascript-filters-cropping-and-more-3192) by codehuntersharath — For the core logic behind the canvas filters and cropping states.
* [Interactive Gradient CodePen](https://codepen.io/MarkBoots/pen/LYjvEJj) by MarkBoots — For the math and styling behind the overlay/difference background gradients.
* [W3Schools CSS Web Safe Fonts](https://www.w3schools.com/cssref/css_websafe_fonts.php) — For the clean Courier monospace font stack.
* [W3Schools HTML Button Links](https://www.w3schools.com/Html/tryit.asp?filename=tryhtml_links_button_element) — For the button setup to jump between the home page and the editor.
* [W3Schools HTML Mark Tag](https://www.w3schools.com/tags/tag_mark.asp) — For the highlighter effect behind the labels so they stay readable against the dark background.

---
Built for Hack Club with 💻, 🍕, and a lot of trial and error!
