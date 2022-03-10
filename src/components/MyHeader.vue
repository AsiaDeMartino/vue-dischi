<template>
  <div class="header">
      <img :src="src" alt="">
  </div>
</template>

<script>
export default {
    name: 'MyHeader',
    data() {
        return {
            src: require("/src/assets/spotify-logo.png")
        }
    }
}
</script>

<style lang="scss" scoped>
.header{
    height: 70px;
    width: 100vw;
    background-color: rgb(35,44,54);
    display: flex;
    align-items: center;
    position: fixed;

    img{
        height: 45px;
        margin-left: 20px;
    }

}
</style>