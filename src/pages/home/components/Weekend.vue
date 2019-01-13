<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
<<<<<<< HEAD
      <li class="item border-bottom" v-for="item in list" :key="item.id">
=======
      <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
>>>>>>> 0276472eb9704d54d5fdd42f7ec4af7233424560
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>

        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
/* eslint-disable  */

export default {
  name: "HomeWeekend",
<<<<<<< HEAD
  props: {
    list: Array
=======
  data() {
    return {
      recommendList: [
        {
          id: "0001",
          imgUrl:
            "https://youimg1.c-ctrip.com/target//10080x000000ldr713E07_C_300_200_Q90.jpg",
          title: "温泉",
          desc: "冬季必备！江浙沪人气泡汤圣地！"
        },
        {
          id: "0002",
          imgUrl:
            "https://youimg1.c-ctrip.com/target//100d0v000000joghmD614_C_300_200_Q90.jpg",
          title: "沙滩海洋",
          desc: "免签！人少！这5个美如天堂的小众海岛，白本护照就能去！"
        },
        {
          id: "0003",
          imgUrl:
            "https://youimg1.c-ctrip.com/target//100e0o000000fcepa623D_C_300_200_Q90.jpg",
          title: "古镇",
          desc: "春节早计划|寻年味、找低价这些地方满足你！"
        }
      ]
    };
>>>>>>> 0276472eb9704d54d5fdd42f7ec4af7233424560
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.title {
  line-height: 0.4rem;
  background: #ccc;
  text-indent: 0.2rem;
}

.item-img-wrapper {
  overflow: hidden;
  height: 0;
<<<<<<< HEAD
  padding-bottom: 37.09%;
=======
  padding-bottom: 33.9%;
>>>>>>> 0276472eb9704d54d5fdd42f7ec4af7233424560
}

.item-img {
  width: 100%;
}

.item-info {
  padding: 0.1rem;
}

.item-title {
  line-height: 0.54rem;
  font-size: 0.32rem;
  ellipsis();
}

.item-desc {
  line-height: 0.4rem;
  color: #ccc;
  ellipsis();
}
</style>
