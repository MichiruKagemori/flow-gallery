# flow-gallery
  
flow-gallery is a zero dependency JavaScript library that allows you to create a justified gallery. It comes with support for responsive images and image captions. Many parts of the gallery are configurable.

## Installation

### Using npm and webpack

```bash
npm install --save flow-gallery
```

```js
import FlowGallery from 'flow-gallery';
```

### Using jsDelivr

Before your closing `</body>` tag add:

```html
<script src="//cdn.jsdelivr.net/npm/flow-gallery@0.1.0/dist/flow-gallery.min.js"></script>
```

### Manual installation

1. Download the latest version from the GitHub releases page and extract it somewhere in your project directory.
2. Then, before your closing `</body>` tag add:

```html
<script src="flow-gallery/dist/flow-gallery.js"></script>
```

## Usage

```html
<div class="flow-gallery">
    <a href="images/originals/1.jpg">
        <img src="images/thumbnails/1.jpg" />
    </a>
    <a href="images/originals/2.jpg">
        <img src="images/thumbnails/2.jpg" />
    </a>
    <a href="images/originals/3.jpg">
        <img src="images/thumbnails/3.jpg" />
    </a>
    <a href="images/originals/4.jpg">
        <img src="images/thumbnails/4.jpg" />
    </a>
</div>
```

```js
var flowGallery = new FlowGallery({
    maxHeight: 300,
    fillLastLine: true
    // ...
});

```

### Using responsive images
Using the `picture` tag with multiple sources is also supported. Only the image with the appropriate size will be loaded. That way you can dramatically decrease the page loading time on devices with a small display. Below you can see an example html.

```html
<div class="flow-gallery">
    <a href="images/originals/1.jpg">
        <picture>
            <source media="(min-width: 1200px)" srcset="images/thumbnails/1-large.jpg" />
            <source media="(min-width: 600px)" srcset="images/thumbnails/1-medium.jpg" />
            <img src="images/thumbnails/1-small.jpg" />
        </picture>
    </a>
    <a href="images/originals/2.jpg">
        <picture>
            <source media="(min-width: 1200px)" srcset="images/thumbnails/2-large.jpg" />
            <source media="(min-width: 600px)" srcset="images/thumbnails/2-medium.jpg" />
            <img src="images/thumbnails/2-small.jpg" />
        </picture>
    </a>
    <a href="images/originals/3.jpg">
        <picture>
            <source media="(min-width: 1200px)" srcset="images/thumbnails/3-large.jpg" />
            <source media="(min-width: 600px)" srcset="images/thumbnails/3-medium.jpg" />
            <img src="images/thumbnails/3-small.jpg" />
        </picture>
    </a>
    <a href="images/originals/4.jpg">
        <picture>
            <source media="(min-width: 1200px)" srcset="images/thumbnails/4-large.jpg" />
            <source media="(min-width: 600px)" srcset="images/thumbnails/4-medium.jpg" />
            <img src="images/thumbnails/4-small.jpg" />
        </picture>
    </a>
</div>
```

### Using captions
You can use captions which will be shown when hovering over an image. To add a caption simply add a div with the `caption` class next to the image. Captions can also be `inverted` by additionally adding the inverted class.

```html
<div class="flow-gallery">
    <a href="images/originals/1.jpg">
        <img src="images/thumbnails/1.jpg" />
        <div class="caption">I`m a caption!</div>
    </a>
    <a href="images/originals/2.jpg">
        <img src="images/thumbnails/2.jpg" />
        <div class="caption inverted">I`m a inverted caption!</div>
    </a>
</div>
```

## Options

| Option         | Type    | Default       | Description                                                        |
| -------------- | ------- | ------------- | ------------------------------------------------------------------ |
| `selector`     | string  | .flow-gallery | The selector for the gallery component                             |
| `maxHeight`    | number  | 400           |The maximum height of a row                                         |
| `gapWidth`     | number  | 10            | The size of the gaps between the images                            |
| `percent`      | boolean | false         | Interpret the sizes as percentage, not as pixels                   |
| `fillLastLine` | boolean | false         | Enlarge images to fill up the last row                             |
| `enlarge`      | boolean | false         | Allow enlargement of images                                        |
| `align`        | string  | left          | Alignment of the images in the last row if the row isn't filled up |

## Methods
Methods are called on flow-gallery instances, see below:

```js
var flowGallery = new FlowGallery();
flowGallery.update();
```

| Method       | Arguments | Description                                  |
| ------------ | --------- | -------------------------------------------- |
| `update`     | -	       | Add newly added images to the gallery layout |
| `fullUpdate` | -	       | Re-create the whole gallery layout           |

## Versioning
This project uses SemVer for versioning. For the versions available, see the tags on this repository.

## License
This project is licensed under the MIT License.
