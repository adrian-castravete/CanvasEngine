# Create a scene

Scenes can prepare the elements and display them on the screen

```javascript
var canvas = CE.defines("canvas_id").
    ready(function() {
        canvas.Scene.call("MyScene");
    });
        
canvas.Scene.new({
    name: "MyScene", // Obligatory
    materials: {
        images: {
            img_id: "path/to/img.png"
        }
    },
    called: function(stage) {

    },
    preload: function(stage, pourcent, material) {

    },
    ready: function(stage, params) {
      
    },
    render: function(stage) {
      
    },
    exit: function(stage) {

    }
});
```

The `materials` property loads images, sounds, videos, etc… See [Materials.load()][materials_load] for more details

The scene is composed of several methods. All methods are optional.

* `called` : `(>=1.3.2)` Method called when the scene call method is called. The images are not loaded. It is impossible to use methods such as `drawImage` on an element
* `preload` : Method called for each resource loaded from the `materials` property list
* `ready`: Method called when all the resources are loaded. To use custom parameters provide the `params` argument:

    ```javascript
    canvas.Scene.call("MyScene", {
        params : "foo"
    });
    ```

    and in the `ready` method use them as the second positional argument:

    ```javascript
    ready: function(stage, params) {
        console.log(params); // displays foo
    }
    ```

* `render`: Method called for each frame render (60 FPS, defined by `requestAnimationFrame()`. Unchangeable)
* `exit`: Method called when this scene is quitted (or another scene is called)

To call the scene:

```javascrtipt
canvas.Scene.call("MyScene");
```

The name of the scene is set in the `name` parameter. See [Scene.call()][scene_call] for more details

The `stage` parameter is the main element. Child elements will be added to the `stage` element

## Quick Example ##

<jsfiddle>WebCreative5/4hySx</jsfiddle>

[materials_load]: http://canvasengine.net/doc/?p=core.materials.load "core.materials.load"
[scene_call]: http://canvasengine.net/doc/?p=core.scene.call "core.scene.call"

