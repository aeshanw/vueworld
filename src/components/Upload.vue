<template>
    <div id="app">
        <vue-dropzone 
        ref="myVueDropzone"
        id="dropzone" 
        :options="dropzoneOptions"
        @vdropzone-complete="afterComplete">
        </vue-dropzone>
    </div>
    </template>
<script>
import vue2Dropzone from 'vue2-dropzone'
import 'vue2-dropzone/dist/vue2Dropzone.min.css'
export default {
  name: 'Upload',
  components: {
    vueDropzone: vue2Dropzone
  },
  methods: {
    afterComplete(file) {
      console.log(file);
      
    }
  },
  data: function () {
    return {
      dropzoneOptions: {
          url: 'https://httpbin.org/post',
          thumbnailWidth: 150,
          maxFilesize: 0.5,
          addRemoveLinks: true,
          headers: { "My-Awesome-Header": "header value" }
      }
    }
  }
} 
</script>   
