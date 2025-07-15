This article details the implementation of a bespoke play/pause/replay button for an embedded Vimeo video. It outlines how the button's visual elements, namely the play and pause icons, are generated purely through CSS, without reliance on image files. The accompanying JavaScript then orchestrates the button's visibility and functionality, enabling seamless interaction with the Vimeo Player SDK to control video playback and respond to player states such as playing, paused, or ended.

<img width="1320" height="1108" alt="image" src="https://github.com/user-attachments/assets/59952f8c-686f-4f77-8684-64efd982e86c" />


Here's a breakdown:


### HTML Structure
The `mainCustomButton` div acts as the container for your custom button. Inside this, a nested div is dynamically created and assigned either the `icon-play` or `icon-pause` class.

~~~```html
<div id="mainCustomButton" class="custom-button">
    <div class="icon-play"></div>
</div>
~~~


### CSS for 'Play' Icon (.icon-play)
The play icon (a triangle) is created using CSS `border-style` properties on a div element. By setting specific border widths and colours for transparent and a solid colour, a triangular shape is formed.

~~~```css
.custom-button .icon-play {
    content: ''; /* Not strictly needed for a div, but often seen with pseudo-elements */
    width: 0;
    height: 0;
    border-style: solid;
    border-width: 15px 0 15px 25px; /* Creates the triangle shape */
    border-color: transparent transparent transparent #fff; /* White triangle */
}
~~~


### JavaScript (updateButtonIcon function)
The `updateButtonIcon` JavaScript function is responsible for dynamically clearing the current icon and appending a new div with the appropriate class (`icon-play` or `icon-pause`) to `mainCustomButton`, thereby changing the visual representation of the button.

