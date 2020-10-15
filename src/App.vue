<template>
  <div id="app">
  <h3>Slider app</h3>
  <Carousel 
  :carousel_data="sliderItems"
  :interval="2000"
  />
  </div>
</template>

<script>
import Carousel from './components/carousel'

export default {
  name: 'App',
  components: {
    Carousel
  },
  data() {
    return {
      sliderItems: [
        {id: 1, title:'slide1', filename: '1.jpg'},
        {id: 2, title:'slide2', filename: '2.jpg'},
        {id: 3, title:'slide3', filename: '3.jpg'},
      ]
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
p{
  color: #000;
}
</style>
