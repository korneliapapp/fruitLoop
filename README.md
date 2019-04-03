## API Lab- fuitLoop
This is the API Lab for the Programming II Couse part of the Bachelor of Science in Interaction Design at Malmö Universitet.
This Lab and its coding examples were executed by Josefine Lagerstedt, Melika Ljutovic, Kornelia Papp, and Therese Casio Persson. Based on the AOS- Animate on scroll library https://github.com/michalsnik/aos, these examples utilize the scroll animations and the elements the library offers to create new and exciting websites/animations.  

---


### About the Library
AOS is a Small library to animate elements on your page as you scroll, it allows you to animate elements as you scroll down, and up.If you scroll back to top, elements will animate to it's previous state and become ready to animate again when you scroll back down.

---


### About the project

In these five example presented, we explored not only the animations that the library presented, but also speed, duration, anchor placements, other custom animations, and so on. We made these animations come to life by recreating interactive websites that could be made use of. 

---



## Our examples

### Example 1:
Example 1 explores scroll speed and scroll duration when scrolling through the website. The speed code is inspired by another code pen example: (https://codepen.io/JTParrett/pen/BkDie). The speed duration function is a predefined option in the AOS library and allows to be manipulated with. 

### Example 2:
Example 2 uses the following animation example from code pen: (https://codepen.io/michalsnik/pen/EyxoNm?fbclid=IwAR2wXceBymvXnZrTRofTi5w9Zd-0OnJjFCyyRFezWbixEuAhsaqsilFVRus)and explores the possibility of using anchor points and anchor-placements based off of the scroll position. This example illustrates a way to create interactive stories through scrolling and to have images react to each other, creating a fun and virtual environment.

### Example 3: 
Example 3 uses the demo of the original AOS library http://michalsnik.github.io/aos/ as well as custom animations from this CodePen example that explores the same library https://codepen.io/michalsnik/pen/WxvNvE. It explores how content can pop up while a static background is visible and how the animated content popping up using different animations can enhance engagement and interest from viewers.

### Example 4:
Example 4 uses the following animation example from code pen: (http://codepen.io/michalsnik/pen/WxvNvE). It explores how content could be shown on websites through different animations such as: scrolling down while the background of an element changes from red to green to highlight a change. In this example instead of the background changing from red to green, we included a diagram to appear with the product as you scroll down to indicate properties of the product. This could be useful for interactive online menus, for example.

### Example 5:
Example 5 uses the demo of the original AOS library http://michalsnik.github.io/aos/. Taking the original demo with simply styled divs with text animating in on scroll, we incorporated graphics and more diverse animations to make the website come to life. This example is different from the other one created (interactive banana recipe) as it plays with an on-click event listener. However, the library does not respond to clicks, only scrolls, so we managed to cheat the system by making it appear as the animations are triggered by click by adding an event listener that scrolls down 800px on every click that shows the next row of graphics.

---



## Setting up/ Installing AOS

To set up and install the AOS library, you may use three different methods:

- Use `bower` by inputting this in the terminal

> bower install aos --save


- Use `npm` by inputting this in the terminal 

 > npm install aos --save
    

- You can also simply download the package directly into your local storage -> [click here](https://github.com/michalsnik/aos/archive/master.zip)

---


### How to link styles
To link styles into your your html file without creating an external css file in the same folder, simply link it by inserting this to in the <head> component. 

```html
  <link rel="stylesheet" href="bower_components/aos/dist/aos.css" />
```

---

### How to add scripts
To add javascript into your your html file without creating an external js file in the same folder, simply add it by inserting this to in the <body> section under the main code. 

```html
  <script src="bower_components/aos/dist/aos.js"></script>
```

---

### To trigger AOS, use INIT
In the javascript file (if you have one) or in the <script> section on your html file, input below. 

```javascript
  <script>
    AOS.init();
  </script>
```
By using init, you're initializing AOS as it's exposed as a global variable.

---


## How to use the AOS library? 

  All you have to do is to add `data-aos` attribute to html element, like so:

```html
  <div data-aos="animation_name">
```

  The javacript will trigger the animation on this element when you scroll to it.
  

### Animations predefined in the library

There are some animations predefined in the library right on AOS, to see them in order to utilize them, visit the demo page by michalsnik http://michalsnik.github.io/aos/

These animations include:
- Fade animations
- Flip animations
- Slide animations
- Zoom animations

Other elements predefined options also include
- Anchor placements
- Easing functions


### Advanced settings predefined in the library

The AOS library also has predefined Advanced settings such as

  - data-aos-offset (this changes the offset to trigger animations either sooner, or later)
  - data-aos-duration (this manipulates the duration of the animation)
  - data-aos-easing (this aids you in choosing a timing function to ease elements in different ways)
  - data-aos-delay (this delays animations by milliseconds) 
  - data-aos-anchor (this is the anchor element, its offset will be counted to trigger animation instead of elements)
  - data-aos-anchor-placement (this setting defines which position of the element on the screen should trigger animation: see example 2 for example of anchor placement)
  - data-aos-once (this defines the animation to be fired once or not, it is to be called by a boolean) 

---
