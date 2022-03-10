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
    width: 200px;
    display: flex;
    flex-direction: column;
    align-items: center;
    color: white;
    background-color: rgb(35,44,54);
    padding: 20px;
    text-align: center;


    figure{
        width: 160px;
        height: 160px;
        flex-shrink: 1;
        margin-bottom: 15px;

        img{
            height: 100%;
            object-fit: cover;
        }
    }

    h1{
        text-transform: uppercase;
        font-size: 25px;
        margin-bottom: 20px;
    }

    span{
        color: grey;
        font-size: 15px;
        margin-bottom: 3px;
    }
}
</style>