<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content"></div>
  </div>
</template>

<script>
/* eslint-disable*/

import DetailBanner from "./components/Banner";
import DetailHeader from "./components/Header";

export default {
  name: "Detail",
  components: { DetailBanner, DetailHeader }
};
</script>
<style lang="stylus" scoped>
.content {
  height: 50rem;
}
</style>
