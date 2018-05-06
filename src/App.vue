<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  margin-top: 60px;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
</style>
