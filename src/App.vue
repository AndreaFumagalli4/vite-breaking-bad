<script>
import { store } from './store.js';
import axios from 'axios';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default{
  components: {
    AppHeader,
    AppMain
  },

  data() {
    return {
      store,
      cardsList: [],
    }
  },

  methods: {
    getCards() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0 ', {
        params: {

        }
      })
      .then((response) => {
        console.log(response.data.data);
        this.cardsList = response.data.data;
      })
      .catch(function (error) {
        console.log(error);
      })
    }
  },

  created() {
    this.getCards();
  }
}
</script>

<template>

  <header>
    <AppHeader />
  </header>

  <main>
    <AppMain />
  </main>

</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;

  header{
    height: 90px;
  }

  main {
    background-color: $bg-main-color;
  }

</style>
