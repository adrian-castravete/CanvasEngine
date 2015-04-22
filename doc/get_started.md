# Get Started

Follow the steps below to start:

1. Download the code `canvasengine-X.Y.Z.all.min.js` on Github or this website
1. Add this code in your page:
    ```html
    <!DOCTYPE html>
    <script src="canvasengine-X.Y.Z.all.min.js"></script>
    <canvas id="canvas_id" width="640" height="480"></canvas>
    ```
    > To use a DOM layer `(>=1.3.1)`
    > ```html
    > <div id="canvas_id" width="640" height="480"></div>
    > ```

1. Initialize the canvas in your JS file :

    ```javascript
    var canvas = CE.defines("canvas_id").ready(function() {

    });
    ```

Method `ready` is called when the canvas is ready (DOM loaded)

