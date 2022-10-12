<template>
  <div class="visual">
    <swiper
    :navigation="true"
    :modules="modules"
    v-bind="swiperOptions"
    :loop="true"
    :pagination="{
        clickable: true,
      }"
    class="mySwiper"
    >
      <swiper-slide
        v-for="(item,i) in swiperView"
        :key="item"
        :style="{'background-color':`${swiperView[i].color}`}"
      >
        <!-- <div :style="{'background-color':`${item.color}`}" class="innerItem"> -->
        <div class="innerItem">
          <img :src="`./images/swiper/${item.src}`" alt="">
        </div>
      </swiper-slide>
    
    </swiper>
    <div class="btnWrap">
      <div class="prev">이전</div>
      <div class="next">다음</div>
    </div>
  </div>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/navigation";
import "swiper/css/pagination";


// import required modules
import { Navigation,Pagination } from "swiper";

//swiper data
import sData from "@/data/swiper.js"

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation,Pagination],
      swiperView:sData,
      swiperOptions:{
        loop:true,
        navigation:{
          nextEl:'.visual .next',
          prevEl:'.visual .prev',
        },
        pagination:{
          type:'fraction'
        }
      }
    };
  },
};
</script>
<style lang="scss">
  .mySwiper{
    .swiper-slide{
      height: 400px;
      .innerItem{ 
        height: 100%;
      }
      img{
        display: block;
        margin:0 auto
      }
    }
  }
  .visual{
    position: relative;
    .btnWrap{
      gap:10px;
      display: flex;
      position: absolute;
      bottom: 20px;
      z-index: 10;
      left: calc( 50% + 300px );
      .next,.prev{
        padding: 5px 10px;
        background: rgba(0,0,0,0.3);
        border-radius: 10px;
        color: white;
        cursor: pointer;
      }
    }
  }
</style>