<script>
import { store } from '../store.js';
import axios from 'axios';

export default{
  name: 'AppMain',

  data() {
    return {
      store,
      cardsList: []
    }
  },

  methods: {
    getCards() {
      
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0 ', {
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
    <div class="card-album">
      <div class="card-container">
        <section class="card-number">
          <p>
            Found tot cards
          </p>
        </section>
        <section class="cards">
          <p v-for="card in cardsList">
            {{ card.name }}
          </p>
        </section>
      </div>
    </div>
  </section>

</template>

<style lang="scss" scoped>
  div.card-album {
    height: 500px;
    max-width: 1250px;
    margin: 0 auto;
    padding: 5rem;
  }

  div.card-container {
    padding: 2rem;
    height: 450px;
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
