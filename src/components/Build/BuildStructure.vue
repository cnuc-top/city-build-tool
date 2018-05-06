<style lang='stylus'>
.build-structure {
  height: 800px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;

  .structure {
    margin: 0 auto;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    clip-path: url('#structure-clip');
  }

  .build-layers {
    overflow: hidden;
    position: relative;

    .svg-path {
      position: absolute;
      bottom: 0px;
      left: 0px;
    }
  }

  .build-svg {
    position: absolute;
    left: 0px;
    top: 0px;
    opacity: 0.1;
  }

  #structure-clip {
    fill: rgba(0, 0, 0, 0);
  }

  .structure-clip {
    position: absolute;
    bottom: 0px;
    left: 0px;
  }

  #structure-layers {
    fill: rgba(0, 0, 0, 0);
    opacity: 1;
    stroke: #777;
  }
}
</style>
<template>
  <div class="build-structure">
    <div class="structure" :style="{width: width + 'px', height: height + 'px'}">
      <div class="build-layers">
        <svg-path :width="width" :height="height" :path="path" id="structure-layers"></svg-path>
        <build-layer :height="layerHeight" v-for="(item, index) in layersDataNow" :key="index"></build-layer>
      </div>
      <svg-path :clip="true" class="structure-clip" :width="width" :height="height" :path="path" id="structure-clip"></svg-path>
    </div>
  </div>
</template>

<script>
import BuildLayer from '@/components/Build/BuildLayer'
import SvgPath from '@/components/Svg/SvgPath'
export default {
  components: { BuildLayer, SvgPath },

  props: {
    width: Number,
    height: Number,
    path: String,
    layers: Number,
    layersDetail: Array,
    layersNow: Number
  },

  data() {
    return {

    }
  },

  computed: {
    layersData() {
      const arr = new Array(this.layers)
      arr.fill(0)
      return arr
    },
    layersDataNow() {
      const arr = new Array(this.layersNow)
      arr.fill(0)
      return arr
    },
    layerHeight() {
      return this.height / this.layers
    }
  },

  mounted() {

  },

  methods: {}
}
</script>
