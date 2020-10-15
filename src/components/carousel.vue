<template>
  <div class="wrapper">
    <div class="carousel" :style="{'margin-left': '-' + (102 * currentSlideIndex) + '%' }">
      <CarouselItem
      v-for="item in carousel_data"
      :key="item.id"
      :item_data="item"
    />
    </div>
    <button class="cbtn" @click="prevSlide">Prev</button>
    <button class="cbtn" @click="nextSlide">Next</button>
  </div>
</template>

<script>
import CarouselItem from './carousel-item'

export default{
  name: "Carousel",
  components: {
    CarouselItem
  },
  props: {
    carousel_data: {
      type: Array,
      default: () => []
    },
    interval: {
      type: Array,
      default: () => []
    }
  },
  data(){
    return{
      currentSlideIndex:0
    }
  },
  methods:{
    prevSlide() {
      if (this.currentSlideIndex > 0) {
        this.currentSlideIndex--
      }
    },
    nextSlide() {
      if (this.currentSlideIndex >= this.carousel_data.length -1) {
        this.currentSlideIndex = 0
      } else {
        this.currentSlideIndex++
      }
    }
  },
  mounted() {
    if(this.interval > 0) {
      let sld = this;
      setInterval(function() {
        sld.nextSlide()
      }, sld.interval)
    }
  }
}
</script>

<style scoped>
.wrapper {
  width: 100%;
  overflow: hidden;
}
.carousel {
  display: flex;
  transition: all ease .5s;
}
.cbtn {
  background: royalblue;
  color: white;
  border: none;
  margin: 0.5rem;
  padding: 0.5rem;
}

</style>
