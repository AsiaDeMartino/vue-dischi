<template>
  <div id="app">
    <MyHeader />
    <MyMain />
  </div>
</template>

<script>
import MyMain from './components/MyMain.vue'
import MyHeader from './components/MyHeader.vue'
import "@fontsource/abel"


export default {
  name: 'App',
  components: {
    MyMain,
    MyHeader,
  }
}
</script>

<style lang="scss">
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Abel";
}

img {
    max-width: 100%;
    display: block;
}

</style>
