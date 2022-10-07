<template>
  <div class="visual">
    <Swiper>
      <SwiperSlide>test1</SwiperSlide>
      <SwiperSlide>test2</SwiperSlide>
      <SwiperSlide>test3</SwiperSlide>
    </Swiper>
  </div>
</template>

<script>
  import { Swiper,SwiperSlide } from "swiper/vue";
  import "swiper/css"
export default {
  components:{
    Swiper,
    SwiperSlide,
  }
}
</script>
  
<style lang="scss">
    .visual{
        height: 300px;
        background: pink;
        
    }
</style>