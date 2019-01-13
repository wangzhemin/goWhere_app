<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item in swiperList" v-bind:key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>

      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
/* eslint-disable  */

export default {
  name: "HomeSwiper",
  data() {
    return {
      swiperOption: {
        pagination: {
          el: ".swiper-pagination"
        },
        loop: true,
        autoplay: true
      },
      swiperList: [
        {
          id: "0001",
          imgUrl:
            "http://dimg04.c-ctrip.com/images/70060y000000lvlou6C83_1242_248_25.jpg"
        },
        {
          id: "0002",
          imgUrl:
            "http://dimg04.c-ctrip.com/images/700p10000000o9xal819D_1242_248_25.jpg"
        },
        {
          id: "000",
          imgUrl:
            "http://dimg04.c-ctrip.com/images/700q0z000000ncgg65B4B_1242_248_25.jpg"
        }
      ]
    };
  }
};
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active {
  background-color: aqua !important;
}

.wrapper {
  width: 100%;
  height: 0;
  overflow: hidden;
  padding-bottom: 31.25%;
  background-color: #eee;
}

.swiper-img {
  width: 100%;
}
</style>
