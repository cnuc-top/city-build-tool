<style lang='stylus'>
.build-base {
  &__cube {
    width: 100px;
    height: 20px;
    margin: 0 auto;
    background: #AAA;
  }

  &__ground {
    height: 20px;
    background: #CCC;
  }

  &__bars {
    height: 200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
  }

  &__bar {
    width: 1px;
    background: #CCC;
  }
}
</style>
<template>
  <div class="build-base">
    <div class="build-base__ground">
      <div class="build-base__cube" :style="{width: w}"></div>
    </div>
    <div class="build-base__bars" :style="{width: w, height: barsHeight}">
      <div class="build-base__bar" v-for="(item, index) in bars"></div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},

  props: {
    width: Number,
    height: Number,
  },

  data() {
    return {

    }
  },

  computed: {
    w() {
      return this.width + 80 + 'px'
    },
    barsHeight() {
      return this.height / 10 + 'px'
    },
    bars() {
      const num = parseInt(this.width / 3)
      const arr = new Array(num)
      arr.fill(0)
      return arr
    }
  },

  mounted() { },

  methods: {}
}
</script>
