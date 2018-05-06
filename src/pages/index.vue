<style lang='stylus'>
.main {
  border: 1px solid #CCC;
  width: 500px;
  height: 1000px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
}
</style>
<template>
  <div>
    <div class="main">
      <build-structure :width="width" :height="height" :layers="layers"></build-structure>
      <build-base :width="width" :height="height"></build-base>
    </div>
  </div>
</template>

<script>
import BuildBase from '@/components/Build/BuildBase'
import BuildStructure from '@/components/Build/BuildStructure'
import BuildSecound from '@/components/Build/BuildSecound'
export default {
  components: { BuildBase, BuildStructure, BuildSecound },

  props: {
  },

  data() {
    return {
      height: 492,
      width: 82,
      layers: 101,
      layersUnder: 3,
      layersDetail: [
        [1, 3, 4.2],
        [4, 101, 3]
      ],
      process: {
        basic: 100,
        layers: 5,
        second: 6
      }
    }
  },

  computed: {},

  mounted() {

  },

  methods: {}
}
</script>
