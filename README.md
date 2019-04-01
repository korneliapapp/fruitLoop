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

### Our examples
Example 1:
Example 2:
Example 3: 
Example 4:
Example 5:

---



### Setting up/ Installing AOS

- Using `bower`

    ```bash
      bower install aos --save
    ```

- Using `npm`

    ```bash
      npm install aos --save
    ```

- Direct download -> [click here](https://github.com/michalsnik/aos/archive/master.zip)


### Link styles

```html
  <link rel="stylesheet" href="bower_components/aos/dist/aos.css" />
```

### Add scripts

```html
  <script src="bower_components/aos/dist/aos.js"></script>
```

AOS from version `1.2.0` is available as UMD module, so you can use it as AMD, Global, Node or ES6 module.

### Init AOS

```javascript
  <script>
    AOS.init();
  </script>
```

## 🤔 How to use it?

### Basic usage

  All you have to do is to add `data-aos` attribute to html element, like so:

```html
  <div data-aos="animation_name">
```

  Script will trigger "animation_name" animation on this element, if you scroll to it.

  [Down below](https://github.com/michalsnik/aos#-animations) is a list of all available animations for now :)

### 🔥 Advanced settings

These settings can be set both on certain elements, or as default while initializing script (in options object without `data-` part).

| Attribute | Description | Example value | Default value |
|---------------------------|-------------|---------------|---------|
| *`data-aos-offset`* | Change offset to trigger animations sooner or later (px) | 200 | 120 |
| *`data-aos-duration`* | *Duration of animation (ms) | 600 | 400 |
| *`data-aos-easing`* | Choose timing function to ease elements in different ways | ease-in-sine | ease |
| *`data-aos-delay`* | Delay animation (ms) | 300 | 0 |
| *`data-aos-anchor`* | Anchor element, whose offset will be counted to trigger animation instead of actual elements offset | #selector | null |
| *`data-aos-anchor-placement`* | Anchor placement - which one position of element on the screen should trigger animation | top-center | top-bottom |
| *`data-aos-once`* | Choose wheter animation should fire once, or every time you scroll up/down to element | true | false |

*Duration accept values from 50 to 3000, with step 50ms, it's because duration of animation is handled by css, and to not make css longer than it is already I created implementations only in this range. I think this should be good for almost all cases.

If not, you may write simple CSS on your page that will add another duration option value available, for example:

```css
  body[data-aos-duration='4000'] [data-aos], [data-aos][data-aos][data-aos-duration='4000']{
    transition-duration: 4000ms;
  }
```

This code will add 4000ms duration available for you to set on AOS elements, or to set as global duration while initializing AOS script.

Notice that double `[data-aos][data-aos]` - it's not a mistake, it is a trick, to make individual settings more important than global, without need to write ugly "!important" there :)

`data-aos-anchor-placement` - You can set different placement option on each element, the principle is pretty simple, each anchor-placement option contains two words i.e. `top-center`. This means that animation will be triggered when `top` of element will reach `center` of the window.
`bottom-top` means that animation will be triggered when `bottom` of an element reach `top` of the window, and so on.
Down below you can find list of all anchor-placement options.

#### Examples:

```html
  <div data-aos="fade-zoom-in" data-aos-offset="200" data-aos-easing="ease-in-sine" data-aos-duration="600">
```
```html
  <div data-aos="flip-left" data-aos-delay="100" data-aos-anchor=".example-selector">
```
```html
  <div data-aos="fade-up" data-aos-anchor-placement="top-center">
```


#### API

AOS object is exposed as a global variable, for now there are three methods available:

  * `init` - initialize AOS
  * `refresh` - recalculate all offsets and positions of elements (called on window resize)
  * `refreshHard` - reinit array with AOS elements and trigger `refresh` (called on DOM changes that are related to `aos` elements)

Example execution:
```javascript
  AOS.refresh();
```

By default AOS is watching for DOM changes and if there are any new elements loaded asynchronously or when something is removed from DOM it calls `refreshHard` automatically. In browsers that don't support `MutationObserver` like IE you might need to call `AOS.refreshHard()` by yourself.

`refresh` method is called on window resize and so on, as it doesn't require to build new store with AOS elements and should be as light as possible.

### Global settings

If you don't want to change setting for each element separately, you can change it globally.

To do this, pass options object to `init()` function, like so:

```javascript
  <script>
    AOS.init({
      offset: 200,
      duration: 600,
      easing: 'ease-in-sine',
      delay: 100,
    });
  </script>
```

#### Additional configuration

These settings can be set only in options object while initializing AOS.

| Setting | Description | Example value | Default value |
|---------------------------|-------------|---------------|---------|
| *`disable`* | Condition when AOS should be disabled | mobile | false |
| *`startEvent`* | Name of event, on which AOS should be initialized | exampleEvent | DOMContentLoaded |

##### Disabling AOS

If you want to disable AOS on certain device or under any statement you can set `disable` option. Like so:

```javascript
  <script>
    AOS.init({
      disable: 'mobile'
    });
  </script>
```

There are several options that you can use to fit AOS perfectly into your project, you can pass one of three device types:
`mobile` (phones and tablets), `phone` or `tablet`. This will disable AOS on those certains devices. But if you want make your own condition, simple type your statement instead of device type name:

```javascript
  disable: window.innerWidth < 1024
```

There is also posibility to pass a `function`, which should at the end return `true` or `false`:

```javascript
  disable: function () {
    var maxWidth = 1024;
    return window.innerWidth < maxWidth;
  }
```

##### Start event

If you don't want to initialize AOS on `DOMContentLoaded` event, you can pass your own event name and trigger it whenever you want. AOS is listening for this event on `document` element.

```javascript
  <script>
    AOS.init({
      startEvent: 'someCoolEvent'
    });
  </script>
```


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
