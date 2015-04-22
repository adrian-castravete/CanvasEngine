# Create an element

Elements are created in the scene :

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
    ready: function(stage) {
        this.element = this.createElement();
        this.element.drawImage("img_id");
        stage.append(this.element);
    },
    render: function(stage) {
        this.element.x += 1;
        stage.refresh();
    }
});
```

In the `ready` method :

1. We create an element with the `createElement` method of this scene
1. `drawImage` method displays an image in the element. We assign the identifier of preloaded image found in the `materials` property
1. We add the newly created element to the scene (the main element) using the `append` method

In the `render` method :

1. We manipulate the element (here, we move it horizontally)
1. We refresh the main element (`stage`) with the `refresh` method

