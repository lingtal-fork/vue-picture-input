vue-picture-input
=============

Mobile-friendly picture file input Vue.js component with image preview, drag and drop, EXIF orientation, and more.

![Picture Input Demo](http://i.giphy.com/3o84UfcY1QV7Unrtba.gif)


## Installation

###npm

``` sh
npm install --save vue-picture-input
```

## Usage

```HTML
<template>
  <div class="hello">    
    <picture-input ref="pictureInput" @change="onChange" width="600" height="600" margin="16" accept="image/jpeg,image/png" size="10" buttonClass="btn"></picture-input>
  </div>
</template>
```

```javascript
<script>
import PictureInput from 'vue-picture-input'

export default {
  name: 'app',
  data () {
    return {
    }
  },
  components: {
    PictureInput
  },
  methods: {
    onChange () {
      console.log('New picture selected!')
      if (this.$refs.pictureInput.image) {
        console.log('Picture loaded.')
      } else {
        console.log('FileReader API not supported: use the <form>, Luke!')
      }
    }
  }
}
</script>
```

## Example project

You can find an example project here: https://github.com/alessiomaffeis/vue-picture-input-example

## Props

- **width, height**: (pixels, optional) the maximum width and height of the preview container. The picture will be resized and centered to cover this area. If not specified, the preview container will expand to full width, 1:1 square ratio.
- **margin**: (pixels, optional) the margin around the preview container. Default value: 0.
- **accept**: (media type, optional) the accepted image type(s), e.g. image/jpeg, image/gif, etc. Default value: 'image/*'. 
- **size**: (MB, optional) the maximum accepted file size in megabytes.
- **id, name**: (string, optional) the id and name attributes of the HTML input element.
- **buttonClass**: (string, optional) the class which will be applied to the 'Change Photo' button.

## Events

- **change**: emitted on (successful) picture change. If you need to access the underlying image from the parent component, add a *ref* attribute to picture-input (see the example above).


## TODOs

- Add support for multiple files (?)
- Demo GitHub pages


## Contributions

All contributions are welcome.
