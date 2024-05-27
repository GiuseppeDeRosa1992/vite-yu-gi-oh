<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import store from './data/store.js'
export default {
  components: {
    AppHeader,
    AppMain,
  },

  data() {
    return {
      //richiamo lo store.js in return per far si che ho lo lista delle cards visibile qui
      store
    }
  },
  created() {
    //creo funzione che mi genera le card tramite un server esterno che poi inietto nella lista delle cards

    axios.get(/*dopo num= decido quante carte creare e dopo offset= decido quante me ne deve saltare di quelle inziali della lista*/"https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0").then(risultato => {

      //dichiaro che in store.js la lista cards è uguale al risultato che mi da la funzione che genera le card
      this.store.cards = risultato.data.data
    })
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style scoped></style>
