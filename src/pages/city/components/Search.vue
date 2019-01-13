<template>
  <div class="search">
    <input type="text" placeholder="输入城市名或拼音" class="search-input">
  </div>
</template>

<script>
/* eslint-disable*/
export default {
  name: "CitySearch"
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.search {
  height: 0.72rem;
  padding: 0.1rem;
  background-color: $bgColor;
}

.search-input {
  box-sizing: border-box;
  width: 100%;
  height: 0.62rem;
  line-height: 0.62rem;
  text-align: center;
  border-radius: 0.06rem;
  color: #666;
  padding: 0 0.1rem;
}
</style>
