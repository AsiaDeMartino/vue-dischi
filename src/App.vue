<template>
  <div id="app">
    <MyMain />
  </div>
</template>

<script>
import MyMain from './components/MyMain.vue'

export default {
  name: 'App',
  components: {
    MyMain
  }
}
</script>

<style lang="scss">
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

img {
    max-width: 100%;
    display: block;
}

</style>
