<template>
  <div class="main">
    <div class="card-wrapper">
        <MyCard v-for="(items, i) in canzoni.response" :key="i" :items="items"/>
    </div>
    
  </div>
</template>

<script>
import axios from 'axios'
import MyCard from './MyCard.vue'

export default {
  name: 'MyMain',
  components: {
    MyCard
  },

  data() {
    return {
      canzoni: [],
    }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then( res => {
      console.log(res.data);
      this.canzoni = res.data;
    });
  },
}
</script>

<style lang="scss" scoped>
.main{
  margin: 0 auto;
  height: 100vh;
  background-color: rgb(23,34,45);
  padding: 150px 200px;
  overflow: scroll;
  display: flex;
  flex-direction: column;
  align-items: center;

    .card-wrapper{
      width: 70vw;
      height: 360px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
      row-gap: 20px;
      column-gap: calc(5% / 4);
    }
}
</style>
