<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div
            class="button-wrapper"
            v-for="item in hot"
            :key="item.id"
            @click="handleCityClick(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) in cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div
            class="item border-bottom"
            v-for="innerItem in item"
            :key="innerItem.id"
            @click="handleCityClick(innerItem.name)"

          >{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable*/
import Bscroll from "better-scroll";
export default {
  name: "CityList",
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper,{
      click:true
    });
  },
  methods: {
    handleCityClick(city) {
      // this.$store.dispatch('changeCity',city)
      this.$store.commit('cityChange',city)
      this.$router.push('/')


      // alert(city)
    }
  },
  watch: {
    letter() {
      if (this.letter) {
        const element = this.$refs[this.letter][0];
        // console.log(element);
        this.scroll.scrollToElement(element);
      }
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list {
  overflow: hidden;
  position: absolute;
  top: 1.78rem;
  left: 0;
  bottom: 0;
  right: 0;
}

.border-topbottom::before, .border-topbottom::after {
  border-color: #ccc;
}

.title {
  line-height: 0.54rem;
  background: #eee;
  padding-left: 0.2rem;
  color: #666;
  font-size: 0.26rem;
}

.button-list {
  padding: 0.1rem;
  overflow: hidden;
  padding: 0.1rem 0.6rem 0.1rem 0.1rem;
}

.button-list .button-wrapper {
  float: left;
  width: 33.33%;
}

.button-wrapper .button {
  margin: 0.1rem;
  text-align: center;
  border: 0.02rem solid #ccc;
  padding: 0.1rem 0;
  border-radius: 0.1rem;
}

.item-list .item {
  line-height: 0.76rem;
  color: #666;
  padding-left: 0.2rem;
}

.item-list .item::before {
  border-color: #ccc;
}
</style>
