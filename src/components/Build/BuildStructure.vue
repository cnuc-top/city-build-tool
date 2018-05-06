<style lang='stylus'>
.build-structure {
  height: 800px;
  background: #EEE;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;

  .structure {
    margin: 0 auto;
    position: relative;
    clip-path: url('#bs-structure');
    // clip-path: circle(30px at 35px 35px);
  }
}

.build-layers {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.build-svg {
  position: absolute;
  left: 0px;
  top: 0px;
  opacity: 0.5;
}
</style>
<template>
  <div class="build-structure">
    <div class="structure" :style="{width: width + 'px', height: height + 'px'}">


      <build-svg></build-svg>
      <div class="build-layers" :style="{width: width + 'px'}">
        <build-layer :height="layerHeight" v-for="(item, index) in layersData" :key="index">1</build-layer>
      </div>
    </div>
  </div>
</template>

<script>
import BuildLayer from '@/components/Build/BuildLayer'
import BuildSvg from '@/components/Build/BuildSvg'
export default {
  components: { BuildLayer, BuildSvg },

  props: {
    width: Number,
    height: Number,
    layers: Number,
    layersDetail: Array
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
    layerHeight() {
      return this.height / this.layers
    }
  },

  mounted() {

  },

  methods: {}
}
</script>
