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
    transition: 0.15s;
  }
}
</style>
<template>
  <div class="build-base">
    <div class="build-base__ground">
      <div class="build-base__cube" :style="{width: w + 'px'}"></div>
    </div>
    <div class="build-base__bars" :style="{width: w + 'px', height: barsHeight + 'px'}">
      <div class="build-base__bar" :style="{height: item + 'px'}" v-for="(item, index) in bars"></div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},

  props: {
    width: Number,
    height: Number,
    process: Number,
  },

  data() {
    return {
      bars: []
    }
  },
  computed: {
    w() {
      return this.width + 40
    },
    barsHeight() {
      return parseInt(this.height / 10)
    }
  },
  mounted() {
    const num = parseInt(this.width / 3)
    const arr = new Array(num)
    arr.fill(0)
    this.lineCount = parseInt(num * this.barsHeight)
    this.bars = arr
    this.barsRandom = this.createArr(num)

    this.mathProcess()
  },

  watch: {
    process: function (val) {
      this.mathProcess()
    }
  },

  methods: {

    mathProcess() {
      let { process, lineCount, bars, barsRandom, barsHeight } = this
      const math = lineCount * (process / 100) / barsHeight
      const num = Math.floor(math)
      bars.fill(0)

      if (num < bars.length) {
        const last = Math.round((math - num) * barsHeight)
        this.$set(bars, barsRandom[num], last)
      }

      if (num === 0) {
        const first =  Math.round((math - num) * barsHeight)
        this.$set(bars, barsRandom[0], first)
      }

      for (let i = 0; i < num; i++) {
        this.$set(bars, barsRandom[i], barsHeight)
      }
    },
    createArr(num) {
      const arr = []
      for (let i = 0; i <= num; i++) {
        arr.push(i)
      }
      arr.sort((a, b) => Math.random() > 0.5 ? -1 : 1)
      return arr
    }
  }
}
</script>
