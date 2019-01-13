<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item in list" v-bind:key="item.id">
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
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: {
          el: ".swiper-pagination"
        },
        loop: true,
        autoplay: true
      }
    };
  },
  computed: {
    showSwiper() {
      return this.list.length;
    }
  }
};
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active {
  background-color: aqua !important;
}

.wrapper {
  width: 100%;
  // height: 0;
  // overflow: hidden;
  // padding-bottom: 31.25%;
  background-color: #eee;
  height: 31.25vw;
}

.swiper-container {
  height: 100%;
}

.swiper-img {
  width: 100%;
  height: 100%;
}
</style>
