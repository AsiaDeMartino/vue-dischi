<template>
  <div class="select">
      <select v-model="scelta" @change="selezionaGenere">
        <option selected :value="'Tutti i generi'">Seleziona un genere</option>
        <option :value="'rock'">Rock</option>
        <option :value="'pop'">Pop</option>
        <option :value="'jazz'">Jazz</option>
        <option :value="'metal'">Metal</option>
</select>
  </div>
</template>

<script>
export default {
    name: 'MySelect',
    data() {
        return {
            scelta:'Tutti i generi',
        }
    },
    methods: {
        selezionaGenere: function() {
            console.log(this.scelta)
            this.$emit('scelta',this.scelta)
        }
    }
}
</script>

<style lang="scss" scoped>
select{
    margin-bottom: 50px;
    padding: 12px 15px 12px 8px;
    background-color: rgba(white,0.1);
    color: white;
    border: 1px solid white;
    border-radius: 3px;
    font-size: 18px;
}

</style>