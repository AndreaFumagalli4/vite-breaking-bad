<script>
import { store } from '../store.js';

import SingleCard from './SingleCard.vue';

export default{
  name: 'CardList',

  components: {
    SingleCard,
  },

  data() {
    return {
      store,
    }
  }
}
</script>

<template>
  <section class="cards">
    <SingleCard v-for="singleCard in store.cardsList" 
    :card="singleCard" />
  </section>
</template>

<style lang="scss" scoped>

  section.cards{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
</style>
