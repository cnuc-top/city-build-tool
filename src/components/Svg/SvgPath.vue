<template>
  <svg class="svg-path" xmlns="http://www.w3.org/2000/svg" :viewBox="'0 0 '+ width + ' ' + height">
    <clipPath :id="id" v-if="clip" :fill="fill">
      <path :d="path" />
    </clipPath>
    <path v-else :id="id" :d="path" :fill="fill" />
  </svg>
</template>

<script>
export default {
  components: {},

  props: {
    id: String,
    clip: {
      type: Boolean,
      default: false
    },
    path: String,
    width: Number,
    height: Number,
    fill: String
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
