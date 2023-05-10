<script>
import FilmComp from './FilmComp.vue';
import SerieComp from './SerieComp.vue';
import {store} from '../store';


export default{
  name: "MainComp",
  components:{
    FilmComp,
    SerieComp
},data(){
  return{
    store
  }
}

}
</script>

<template>
  <div id="container" class="d-flex justify-content-between align-items-center mt-4 ">
    <FilmComp v-for="(element, index) in store.arrayNetflix" :key="index" :propsFilm="element"/>
  </div>
  <div id="container" class="d-flex justify-content-between align-items-center mt-4 ">
    <SerieComp v-for="(element, index) in store.arraySerie" :key="index" :propsSerie="element"/>
  </div>
</template>

<style lang="scss" scoped>
  #container{
    overflow-x: scroll;
    overflow-y: hidden;
    height: 40vh;
    width: 80%;
    margin: 0 auto;
  }
</style>