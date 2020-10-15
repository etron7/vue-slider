<template>
  <div>
    <img :src="require('../assets/slides/' + item_data.filename)" alt="">
  </div>
</template>

<script>
export default{
  name: "CarouselItem",
  props: {
    item_data: {
    type: Object,
    default: () => {}
    },
  },
  data(){
    return{}
  },
  methods:{
  }
}
</script>

<style scoped>
</style>
