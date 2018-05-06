<style lang='stylus'>
.build-svg {
  width: 82px;
  height: 492px;

  svg {
    width: 100%;
    height: 100%;
  }

  .structure {
    // fill: rgba(0, 0, 0, 0);
    stroke: #000;
  }
}

// .cls-1 {
// fill: #8bf0ff;
// }
.cls-2 {
  fill: #333;
}

.cls-3 {
  fill: #111;
}
</style>
<template>
  <div class="build-svg">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 82 492">
      <!-- <defs> -->
      <path class="cls-1" d="M0,0V492H82V0ZM61.86,56.5H20.6l-8.25-42H70.62Z" />
      <clipPath id="bs-structure">
        <path d="M0,0V492H82V0ZM61.86,56.5H20.6l-8.25-42H70.62Z" />
      </clipPath>

      <path class="structure" d="M0,0V492H82V0ZM61.86,56.5H20.6l-8.25-42H70.62Z" />
      <!-- </defs> -->
      <path class="cls-2" d="M82,0V492H40C45.36,279.74,49.55,162.41,82,0Z" />
      <path class="cls-2" d="M0,0V492H42C36.64,279.74,32.45,162.41,0,0Z" />
      <path class="cls-3" d="M82,0H0C30.42,152.25,36,264.88,41,453.25,46,264.88,51.58,152.25,82,0Z" />
      <!-- <polygon class="cls-4" points="12.35 14.5 70.62 14.5 61.85 56.5 20.6 56.5 12.35 14.5" /> -->
    </svg>
  </div>
</template>

<script>

export default {
  components: {},

  props: {
  },

  data() {
    return {
    }
  },

  computed: {},

  mounted() {
  },

  methods: {}
}
</script>
