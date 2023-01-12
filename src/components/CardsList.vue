<script>
import { store } from '../store.js';
import SingleCard from './SingleCard.vue'

export default{
  name: 'CardsList',

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
    <SingleCard v-for="cardEl in store.cardsList" 
    :card="cardEl"/>
  </section>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
  section.cards{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
  }

</style>
