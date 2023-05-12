<script>
import FilmComp from './FilmComp.vue';
import SerieComp from './SerieComp.vue';
import {store} from '../store';
import ProvaCarosello from './ProvaCarosello.vue';


export default{
  name: "MainComp",
  components:{
    FilmComp,
    SerieComp,
    ProvaCarosello
},data(){
  return{
    store
  }
},
methods:{
  scrollHorizzontale(e, elementHtml){
    const container = document.getElementById(elementHtml)
    
    if(e.deltaY > 0){
      container.scrollLeft += 230
    } else {
      container.scrollLeft -= 230
    }
  }
}

}
</script>

<template>
  <h2>Film</h2>
  <div  @wheel.prevent="scrollHorizzontale($event, 'container-film')" id="container-film" class="d-flex justify-content-between align-items-center mt-4 ">
    <FilmComp v-for="(element, index) in store.arrayNetflix" :key="index" :propsFilm="element"/>
  </div>
  <h2 class="mt-5">Serie</h2>
  <div @wheel.prevent="scrollHorizzontale($event, 'container-serie')" id="container-serie" class="d-flex justify-content-between align-items-center mt-4 ">
    <SerieComp v-for="(element, index) in store.arraySerie" :key="index" :propsSerie="element"/>
  </div>
  <h2 class="mt-5">Attori</h2>
  <div id="container-carosello" class="d-flex justify-content-between align-items-center mt-4 mb-5 ">
    <ProvaCarosello/>
  </div>
</template>

<style lang="scss" scoped>
  h2{
    margin-left: 10%;
    color: white;
  }
  #container-film,
  #container-serie{
    overflow-x: hidden;
    overflow-y: hidden;
    height: 50vh;
    width: 80%;
    margin: 0 auto;
  }
  #container-carosello{
    height: 30vh;
    width: 80%;
    margin: 0 auto;
  }
</style>