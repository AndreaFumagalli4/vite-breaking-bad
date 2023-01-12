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
      cardArchetype: 'alien',
    }
  },

  methods: {
    getCards(selectedArchetype) {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0 ', {
        params: {
          archetype: selectedArchetype,
        }
      })
      .then((response) => {
        console.log(response.data.data);
        this.store.cardsList = response.data.data;
        console.log(this.cardArchetype);
      })
      .catch(function (error) {
        console.log(error);
      })
    }
  },

  created() {
    this.getCards(this.cardArchetype);
  }
}
</script>

<template>

  <header>
    <AppHeader />
  </header>

  <main @changeType="getCards(selectedArchetype)">
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
