<script>

export default{
  name: 'AppMain'
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
