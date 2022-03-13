<template>
  <div class="main">
    <MySelect @scelta="scelta" :generi="canzoni" />
    <div class="card-wrapper">
        <MyCard :class="prova2(i) ? '' : 'nascondi'" v-for="(items, i) in canzoni.response" :key="i" :items="items"/>
    </div>
    
  </div>
</template>

<script>
import axios from 'axios'
import MyCard from './MyCard.vue'
import MySelect from './MySelect.vue'

export default {
  name: 'MyMain',
  components: {
    MyCard,
    MySelect,
  },

  data() {
    return {
      canzoni: [],
      prova1:'Tutti i generi',
    }
  },
  methods:{
    scelta: function(selezione){
       console.log(selezione)
       this.prova1=selezione
    },
    prova2: function(j){
      if (this.prova1 == (this.canzoni.response[j].genre).toLowerCase()) {
        return(true)
      } else if (this.prova1 == 'Tutti i generi'){
        return(true)
      } else {
        return(false)
      }
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

    .nascondi{
      display: none;
    }
}
</style>
