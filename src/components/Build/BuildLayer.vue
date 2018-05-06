<style lang='stylus'>
.build-layler {
  border-top: 1px solid #777;
  display: flex;
  justify-content: space-between;
  position: relative;

  &__bar {
    width: 1px;
    background: #CCC;
    height: 100%;

    &:first-child, &:last-child {
      opacity: 0;
    }
  }
}
</style>
<template>
  <div class="build-layler" :style="{height: height + 'px'}">
    <div class="build-layler__bar" v-for="(item, index) in bars" :key="index"></div>
  </div>
</template>

<script>
export default {
  components: {},

  props: {
    height: Number,
    col: {
      type: Number,
      default: 3
    }
  },

  data() {
    return {
    }
  },

  computed: {
    bars() {
      const arr = new Array(this.col + 2)
      arr.fill(0)
      return arr
    }
  },

  mounted() { },

  methods: {}
}
</script>
