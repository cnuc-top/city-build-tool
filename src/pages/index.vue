<style lang='stylus'>
.main {
  border: 1px solid #CCC;
  width: 500px;
  height: 1000px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  // align-items: center;
}

.build-top {
  height: 800px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.build-main {
  position: relative;
  margin: 0 auto;

  .build-structure, .build-secound {
    position: absolute;
    bottom: 0px;
  }

  .build-secound {
    opacity: 0.8;
  }
}
</style>
<template>
  <div>
    <div class="main">
      <div class="build-top">
        <div class="build-main" :style="{width: width + 'px', height: height + 'px'}">
          <build-structure :path="structure" :width="width" :height="height" :layers="layers" :layersNow="process.layers"></build-structure>
          <build-secound :width="width" :height="height" :secounds="secounds"></build-secound>
        </div>
      </div>
      <build-base :width="width" :height="height"></build-base>
    </div>
  </div>
</template>

<script>
import BuildBase from '@/components/Build/BuildBase'
import BuildStructure from '@/components/Build/BuildStructure'
import BuildSecound from '@/components/Build/BuildSecound'
import BuildData from '@/common/data/swfc'
export default {
  components: { BuildBase, BuildStructure, BuildSecound },

  props: {
  },

  data() {
    return {
      ...BuildData,
    }
  },

  computed: {},

  mounted() {

  },

  methods: {}
}
</script>
