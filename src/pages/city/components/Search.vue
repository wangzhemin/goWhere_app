<template>
  <div>
    <div class="search">
      <input type="text" v-model="keyword" placeholder="输入城市名或拼音" class="search-input">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item in list" :key="item.id"
        @click="handleCityClick(item.name)">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到该城市</li>
      </ul>
    </div>
  </div>
</template>

<script>
/* eslint-disable*/
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1
            ) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scorll = new Bscroll(this.$refs.search,{
      click:true
    })
  },
  methods:{
    handleCityClick(city){
      this.$store.commit('cityChange', city)
      this.$router.push('/')
    }
  }
}
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

.search-content {
  position: absolute;
  overflow: hidden;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  // background: red;
  z-index: 1;
}

.search-item {
  line-height: 0.62rem;
  padding-left: 0.2rem;
  color: #666;
  background-color: #fff;
}
</style>
