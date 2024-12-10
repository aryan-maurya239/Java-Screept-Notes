# By Aryan Maurya
---

# JavaScript Events: Full Notes and Event Names

JavaScript events are actions or occurrences that happen in the browser, which JavaScript can respond to. These events can be triggered by user interactions or automatically.

---

## **1. Mouse Events**
Mouse events are triggered by mouse actions like clicks or movement.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `click`          | Triggered when an element is clicked.                           |
| `dblclick`       | Triggered when an element is double-clicked.                    |
| `mousedown`      | Triggered when the mouse button is pressed down.                |
| `mouseup`        | Triggered when the mouse button is released.                    |
| `mousemove`      | Triggered when the mouse is moved over an element.              |
| `mouseenter`     | Triggered when the mouse enters an element (does not bubble).   |
| `mouseleave`     | Triggered when the mouse leaves an element (does not bubble).   |
| `mouseover`      | Triggered when the mouse enters an element or its children.     |
| `mouseout`       | Triggered when the mouse leaves an element or its children.     |
| `contextmenu`    | Triggered when the right mouse button is clicked.               |

---

## **2. Keyboard Events**
Keyboard events are triggered by user interactions with the keyboard.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `keydown`        | Triggered when a key is pressed.                                |
| `keyup`          | Triggered when a key is released.                               |
| `keypress`       | *(Deprecated)* Triggered when a key is pressed (key character). |

---

## **3. Form Events**
Form events are triggered when interacting with form elements.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `submit`         | Triggered when a form is submitted.                             |
| `reset`          | Triggered when a form is reset.                                 |
| `focus`          | Triggered when an element gains focus (does not bubble).        |
| `blur`           | Triggered when an element loses focus (does not bubble).        |
| `input`          | Triggered when the value of an `<input>`, `<textarea>`, or `<select>` changes. |
| `change`         | Triggered when an input field loses focus and its value has changed. |
| `select`         | Triggered when text is selected in an input or textarea.        |

---

## **4. Touch Events**
Touch events are triggered on touch-enabled devices.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `touchstart`     | Triggered when a touch point is placed on the screen.           |
| `touchmove`      | Triggered when a touch point is moved along the screen.         |
| `touchend`       | Triggered when a touch point is removed from the screen.        |
| `touchcancel`    | Triggered when the touch event is canceled (e.g., another app). |

---

## **5. Drag and Drop Events**
Drag and drop interactions trigger these events.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `dragstart`      | Triggered when an element starts being dragged.                 |
| `drag`           | Triggered while an element is being dragged.                    |
| `dragend`        | Triggered when the dragging of an element ends.                 |
| `dragenter`      | Triggered when a dragged item enters a drop zone.               |
| `dragover`       | Triggered when a dragged item is over a drop zone.              |
| `dragleave`      | Triggered when a dragged item leaves a drop zone.               |
| `drop`           | Triggered when a dragged item is dropped into a drop zone.      |

---

## **6. Clipboard Events**
These events deal with copy, paste, and cut actions.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `copy`           | Triggered when content is copied to the clipboard.              |
| `cut`            | Triggered when content is cut to the clipboard.                 |
| `paste`          | Triggered when content is pasted from the clipboard.            |

---

## **7. Focus and Blur Events**
These are specific to elements that can gain focus.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `focus`          | Triggered when an element gains focus.                          |
| `blur`           | Triggered when an element loses focus.                          |

---

## **8. Media Events**
Triggered by media elements like `<audio>` or `<video>`.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `play`           | Triggered when media playback starts.                           |
| `pause`          | Triggered when media playback is paused.                        |
| `ended`          | Triggered when media playback ends.                             |
| `volumechange`   | Triggered when the volume changes.                              |
| `timeupdate`     | Triggered when the current playback position changes.           |
| `loadedmetadata` | Triggered when metadata (e.g., duration) is loaded.             |
| `canplay`        | Triggered when media is ready to play.                          |
| `waiting`        | Triggered when playback is delayed due to buffering.            |

---

## **9. Document Events**
Related to the document or window.

| **Event Name**      | **Description**                                               |
|----------------------|--------------------------------------------------------------|
| `DOMContentLoaded`   | Triggered when the HTML is completely loaded and parsed.     |
| `load`              | Triggered when the entire page (including images) is loaded. |
| `unload`            | Triggered when the page is being unloaded.                   |
| `scroll`            | Triggered when the user scrolls the page.                    |
| `resize`            | Triggered when the browser window is resized.                |

---

## **10. Custom Events**
Custom events allow creating and triggering your own events.

### Example
```javascript
const event = new CustomEvent('myCustomEvent', { detail: { message: 'Hello, World!' } });
document.addEventListener('myCustomEvent', (e) => {
  console.log(e.detail.message); // Output: Hello, World!
});
document.dispatchEvent(event);
```

---

## **11. Pointer Events**
Pointer events unify mouse, touch, and pen input.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `pointerdown`    | Triggered when a pointer (mouse, pen, or touch) is pressed.     |
| `pointerup`      | Triggered when a pointer is released.                           |
| `pointermove`    | Triggered when a pointer is moved.                              |
| `pointerenter`   | Triggered when a pointer enters an element.                     |
| `pointerleave`   | Triggered when a pointer leaves an element.                     |

---

## **12. Animation Events**
Triggered during CSS animations.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `animationstart` | Triggered when an animation starts.                             |
| `animationend`   | Triggered when an animation ends.                               |
| `animationiteration` | Triggered when an animation repeats.                      |

---

## **13. Transition Events**
Triggered during CSS transitions.

| **Event Name**   | **Description**                                                  |
|-------------------|------------------------------------------------------------------|
| `transitionstart`| Triggered when a CSS transition starts.                         |
| `transitionend`  | Triggered when a CSS transition ends.                           |
| `transitioncancel` | Triggered when a CSS transition is canceled.                  |

---

