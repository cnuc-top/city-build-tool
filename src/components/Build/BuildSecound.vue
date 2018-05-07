<style lang='stylus'>
.build-secound {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;

  .svg-path {
    position: absolute;
    left: 0px;
    top: 0px;
    opacity: 0.8;
  }

  &__clip {
    position: absolute;
    top: 0px;
    bottom: 0px;
    right: 0px;
    left: 0px;
  }
}
</style>
<template>
  <div class="build-secound" :style="{width: width + 'px', height: height + 'px'}">
    <div class="build-secound__clip" :style="{clip: 'rect(' + clipHeight + 'px, ' + width + 'px, ' + height + 'px, 0px)'}">
      <svg-path v-for="(item, index) in secounds" :key="index" :width="width" :height="height" :path="item[0]" :fill="item[1]"></svg-path>
    </div>
  </div>
</template>

<script>
import SvgPath from '@/components/Svg/SvgPath'
export default {
  components: { SvgPath },

  props: {
    width: Number,
    height: Number,
    layers: Number,
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
