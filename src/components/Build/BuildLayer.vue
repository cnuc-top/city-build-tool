<style lang='stylus'>
.build-layler {
  height: 5px;
  width: 100%;
  border-top: 1px solid #777;
}
</style>
<template>
  <div class="build-layler" :style="{height: height + 'px'}"></div>
</template>

<script>
export default {
  components: {},

  props: {
    height: Number
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
