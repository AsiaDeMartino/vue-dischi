<template>
  <div class="card">
      <figure>
          <img :src="items.poster" alt="">
      </figure>
      <h1>{{items.title}}</h1>
      <span>{{items.author}}</span>
      <span>{{items.year}}</span>
  </div>
</template>

<script>
export default {
    name: 'MyCard',
    props:{
        items:{}
    }
}
</script>

<style lang="scss" scoped>
.card{
    height: 360px;
    width: calc(100% / 6);
    display: flex;
    flex-direction: column;
    align-items: center;
    color: white;
    background-color: rgba(white,0.1);
    padding: 2%;
    text-align: center;


    figure{
        aspect-ratio: 1;
        width: 100%;
        margin-bottom: 15px;

        img{
            height: 100%;
            
        }
    }

    h1{
        text-transform: uppercase;
        font-size: 1.5em;
        margin-bottom: 20px;
    }

    span{
        color: grey;
        font-size: 1em;
        margin-bottom: 3px;
    }
}
</style>