<style lang='stylus'>
.build-secound {
  position: relative;

  .svg-path {
    position: absolute;
    left: 0px;
    top: 0px;
  }
}
</style>
<template>
  <div class="build-secound" :style="{width: width + 'px', height: height + 'px'}">
    <svg-path v-for="(item, inedx) in secounds" :width="width" :height="height" :path="item[0]" :fill="item[1]"></svg-path>

  </div>
</template>

<script>
import SvgPath from '@/components/Svg/SvgPath'
export default {
  components: { SvgPath },

  props: {
    width: Number,
    height: Number,
    secounds: Number
  },

  data() {
    return {
    }
  },

  computed: {},

  mounted() { },

  methods: {}
}
</script>
