<template>
  <div class="header">城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
/* eslint-disable*/
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  position: relative;
  overflow: hidden;
  height: $headerHeight;
  line-height: $headerHeight;
  text-align: center;
  color: #fff;
  background-color: $bgColor;
}

.header-back {
  width: 0.64rem;
  font-size: 0.4rem;
  position: absolute;
  top: 0;
  left: 0;
  color: #fff;
}
</style>
