<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">

        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
/* eslint-disable  */

export default {
  name: "HomeRecommend",
  data() {
    return {
      recommendList: [
        {
          id: "0001",
          imgUrl:
            "https://dimg07.c-ctrip.com/images/fd/tg/g3/M00/6C/00/CggYGlYgmgKAJDqHABa1BmjqnRc404_C_190_190.jpg",
          title: "三亚自由行",
          desc:
            "三亚5日自由行·初游甄选享早订&多人出行礼遇 | 多一种旅行体验 惊艳朋友圈"
        },
        {
          id: "0002",
          imgUrl:
            "https://dimg07.c-ctrip.com/images/fd/tg/g3/M00/6C/00/CggYGlYgmgKAJDqHABa1BmjqnRc404_C_190_190.jpg",
          title: "三亚自由行",
          desc:
            "三亚5日自由行·初游甄选享早订&多人出行礼遇 | 多一种旅行体验 惊艳朋友圈"
        },
        {
          id: "0003",
          imgUrl:
            "https://dimg07.c-ctrip.com/images/fd/tg/g3/M00/6C/00/CggYGlYgmgKAJDqHABa1BmjqnRc404_C_190_190.jpg",
          title: "三亚自由行",
          desc:
            "三亚5日自由行·初游甄选享早订&多人出行礼遇 | 多一种旅行体验 惊艳朋友圈"
        }
      ]
    };
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

.item {
  display: flex;
  height: 1.9rem;
  overflow: hidden;
}

.item-img {
  width: 1.7rem;
  height: 1.7rem;
  padding: 0.1rem;
}

.item-info {
  flex: 1;
  padding: 0.1rem;
  min-width: 0;
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

.item-button {
  line-height: 0.44rem;
  background: #ff9300;
  padding: 0 0.2rem;
  border-radius: 0.06rem;
  margin-top: 0.16rem;
  color: #fff;
}
</style>
