<script>
import { store } from '../store.js';
import axios from 'axios';

import AppMainCard from './AppMainCard.vue';

export default{
  name: 'AppMain',

  components: {
    AppMainCard,
  },

  data() {
    return {
      store,
      cardsList: []
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
            Found {{ cardsList.length }} cards
          </p>
        </section>
        <section class="cards">
          <AppMainCard v-for="cardEl in cardsList"
          :image="cardEl.card_images[0].image_url"
          :name="cardEl.name"
          :type="cardEl.type" />
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

    section.cards{
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
    }
  }
</style>
