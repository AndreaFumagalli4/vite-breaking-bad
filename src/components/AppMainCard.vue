<script>

export default{
  name: 'AppMainCard',

  props:{
    image: String,
    name: String,
    type: String
  }

}

</script>

<template>
  <div class="card">
    <div>
      <img :src="image" :alt="name">
    </div>
    <h3>
      {{ name }}
    </h3>
    <p>
      {{ type }}
    </p>
  </div>
  
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
  div.card {
    background-color: $bg-main-color;
    width: calc((100% / 5) - 1rem);
    margin-right: 1rem;
    margin-bottom: 1rem;

    &:nth-child(5n+5) {
      margin-right: 0;
    }

    img {
      width: 100%;
    }

    h3,
    p {
      text-align: center;
      padding: .5rem;
    }

    h3 {
      color: white;
      text-transform: uppercase;
      font-size: 1rem;
    }

    p {
      font-size: .9rem;
    }
  }


</style>
