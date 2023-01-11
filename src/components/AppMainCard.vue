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

</style>
