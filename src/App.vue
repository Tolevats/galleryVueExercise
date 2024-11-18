<template>
  <div id="app">
   <ImageGallery />
  </div>
</template>

<script>
import ImageGallery from './components/ImageGallery.vue';

export default {
  name: 'App',
  components: {
    ImageGallery,
  },
};
</script>

<style>
#app {
  box-sizing: border-box;
  margin: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
}
</style>
