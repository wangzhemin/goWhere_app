<template>
  <ul class="list">
    <li
      class="item"
      v-for="item in letters"
      :key="item"
      @click="hangleLetterClick"
      @touchstart="hangleTouchStart"
      @touchmove="hangleTouchMove"
      @touchend="hangleTouchEnd"
      :ref="item"
    >{{item}}</li>
  </ul>
</template>

<script>
/* eslint-disable*/
export default {
  name: "CityAlphabet",
  props: { cities: Object },
  computed: {
    letters() {
      const letters = [];
      for (let i in this.cities) {
        letters.push(i);
      }
      return letters;
    }
  },
  data() {
    return {
      touchStatus: false,
      startY: 0,
      tiemr: null
    };
  },
  updated() {
    this.startY = this.$refs["A"][0].offsetTop;
  },
  methods: {
    hangleLetterClick(e) {
      this.$emit("change", e.target.innerText);
      console.log(e);
    },
    hangleTouchStart() {
      this.touchStatus = true;
    },
    hangleTouchMove(e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer);
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 89;
          const index = Math.floor((touchY - this.startY) / 20);
          if (index >= 0 && index < this.letters.length) {
            this.$emit("change", this.letters[index]);
          }
        }, 16);
      }
    },
    hangleTouchEnd() {
      this.touchStatus = false;
    }
  }
};
</script>


<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;
}

.item {
  line-height: 0.4rem;
  text-align: center;
  color: $bgColor;
}
</style>

