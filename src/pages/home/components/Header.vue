<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>

    <router-link to="/city">
      <div class="header-right">
        {{this.$store.state.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
/* eslint-disable  */

export default {
  name: "HomeHeader"
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  display: flex;
  line-height: $headerHeight;
  background: $bgColor;
  color: #fff;
}

.header-left {
  width: 0.64rem;
  float: left;
}

.header-left .back-icon {
  text-align: center;
  font-size: 0.4rem;
}

.header-input {
  flex: 1;
  margin-top: 0.12rem;
  margin-left: 0.2rem;
  height: 0.64rem;
  line-height: 0.64rem;
  padding-left: 0.2rem;
  background: #fff;
  border-radius: 0.1rem;
  color: #ccc;
}

.header-right {
  width: 1.24rem;
  float: right;
  text-algin: center;
  color: #fff;
}

.header-right .arrow-icon {
  font-size: 0.24rem;
  margin-left: -0.04rem;
}
</style>
