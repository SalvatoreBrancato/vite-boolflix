<script>

export default{
  name: "FilmComp",
  props:['propsFilm']
    
}
</script>

<template>
  <div id="card" class="mx-2 text-center">
    <h3>{{ propsFilm.original_title }}</h3>
    <h4>{{ propsFilm.title }}</h4>
    <h5>{{ propsFilm.original_language }}</h5>
    <h6>{{ propsFilm.vote_average }}</h6>
  </div>
</template>

<style lang="scss">
  #card{
    height: 300px;
    min-width: 200px;
    border: 2px solid black;
  }
</style>