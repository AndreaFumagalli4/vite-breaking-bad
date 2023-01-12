<script>
import { store } from '../store.js';

import CardsList from './CardsList.vue';

export default{
  name: 'AppMain',

  components: {
    CardsList
  },

  data() {
    return {
      store,
    }
  }
}
</script>

<template>

  <section>
    <div class="dropdown-menu">
      <select name="archetype" id="archetype-select">
        <option value="alien">Alien</option>
        <option value="laval">Laval</option>
        <option value="vylon">Vylon</option>
        <option value="inzektor">Inzektor</option>
        <option value="umi">Umi</option>
        <option value="gusto">Gusto</option>
      </select>
    </div>
    <div class="card-album">
      <div class="card-container">
        <section class="card-number">
          <p>
            Found {{ store.cardsList.length }} cards
          </p>
        </section>
      </div>
    </div>
  </section>

</template>

<style lang="scss" scoped>

  div.dropdown-menu {
    max-width: 1250px;
    margin: 0 auto;
    padding: 1rem 6rem;
    
    select {
      height: 30px;
      width: 10%;
    }
  }

  div.card-album {
    max-width: 1250px;
    margin: 0 auto;
    padding: 0 5rem;
  }

  div.card-container {
    padding: 2rem;
    background-color: white;

    section.card-number {
      background-color: #212529;
      color: white;

      p {
        padding: 1rem;
        font-weight: 500;
      }
    }
  }
</style>
