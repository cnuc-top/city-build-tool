<style lang='stylus'>
.main {
  border: 1px solid #CCC;
  width: 500px;
  height: 1000px;
  margin: 0 auto;
}
</style>
<template>
  <div>
    <div class="main">
      <build-base></build-base>
    </div>
  </div>
</template>

<script>
import BuildBase from '@/components/Build/BuildBase'
export default {
  components: { BuildBase },

  props: {
  },

  data() {
    return {
      data: {
        height: 492,
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
    }
  },

  computed: {},

  mounted() {

    var canvas = document.getElementById('myCanvas');
    var ctx = canvas.getContext('2d');
    ctx.fillStyle = '#FF0000';
    ctx.fillRect(0, 0, 80, 100);
  },

  methods: {}
}
</script>
