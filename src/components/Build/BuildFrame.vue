<style lang='stylus'>
.build-frame {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  stroke: #000;
  fill: rgba(0, 0, 0, 0);
  opacity: 0.1;

  .svg-path {
    position: absolute;
    left: 0px;
    top: 0px;
  }
}
</style>
<template>
  <div class="build-frame" :style="{width: width + 'px', height: height + 'px'}">
    <svg-path v-for="(item, index) in secounds" :key="index" :width="width" :height="height" :path="item[0]"></svg-path>
  </div>
</template>

<script>
import SvgPath from '@/components/Svg/SvgPath'
export default {
  components: { SvgPath },

  props: {
    width: Number,
    height: Number,
    process: Number,
    secounds: Array
  },

  data() {
    return {
    }

  },

  computed: {
    clipHeight() {
      return this.height - this.process / this.layers * this.height
    }
  },

  mounted() { },

  methods: {}
}
</script>
