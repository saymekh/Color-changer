# Color Change Hover Effect


This project demonstrates a simple hover effect where the background color 
changes when hovering over the text.

## Demo

Click [here] (https://saymekh.github.io/Color-changer/)


# Step-by-Step Instruction


## Step 1: Setting Up Your Project

1. Create a Project Folder: Make a new folder on your computer to hold your 
project files. You can name it something like ```hover-effect-project```.

2. Create Project Files:

* Inside the project folder, create a file named index.html. This will contain 
your HTML markup. 

* Create another file named styles.css. This will hold the CSS for your hover 
effect.

```html 

<body>
    <div class="container">
        <h1>HOVER OVER ME</h1>
    </div>
</body>

```

```css

body {
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  font-family: system-ui, sans-serif;
}

h1 {
  position: relative;
  font-size: 5rem;
}

h1::before {
  content: " ";
  display: block;
  position: absolute;
  top: 0; right: 0; bottom: 0; left: 0;
  background: #00e600;
  z-index: -1;
  transition: transform .3s ease;
  transform: scaleX(0);
  transform-origin: bottom right;
}

h1:hover::before {
  transform: scaleX(1);
  transform-origin: bottom left;
}

h1:hover {
  color: #7300e6; 
}

```


## Step 3: Style With CSS

* In ```styles.css```, you define styles for the ```h1``` element and its 
```::before```pseudo-element to create the hover effect.
* ```h1::before:``` This selector targets the pseudo-element ```::before``` of 
the ```h1``` tag. It's used to create a layer behind the text. You set its 
```transform``` property to ```scaleX(0)``` to initially hide this layer. 
The ```transform-origin``` property is set to ```bottom right```, meaning 
the scaling effect will expand from that origin.
* ```h1:hover::before:``` This changes the ```transform``` of the ```::before``` 
pseudo-element to ```scaleX(1)``` when the ```h1``` is hovered, making the 
pseudo-element fully visible and thus changing the background color behind 
the text. The ```transform-origin``` shifts to ```bottom left```, so the 
expansion effect appears to move across from left to right.
* ```h1``` Styling: You set the ```position``` to ```relative``` to establish a 
stacking context for the absolutely positioned ```::before``` pseudo-element. 
The font size and other styling properties like ```color``` are also defined 
here.
* Global Styles: The ```html``` and ```body``` selectors are styled to ensure 
the page takes up the full viewport height and width, with the content centrally 
aligned. This provides a neat and centered appearance for the demonstration.


## Step 4: Link CSS to HTML

* In ```index.html``` ```<head>```, link ```styles.css``` using ```<link>```tag.


## Step 5: Understanding The Code


* The Hover Effect: When you hover over the ```h1``` element with your mouse, 
the CSS ```:hover``` selector activates the styles defined under 
```h1:hover::before```. The ```::before``` pseudo-element transitions from a 
```scaleX(0)``` (invisible) to ```scaleX(1)``` (fully visible), revealing the 
background color animation that appears to fill the space behind the text from 
one side to the other.
