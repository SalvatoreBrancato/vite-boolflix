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
  <FilmComp/>
  <SerieComp/>
</template>

<style lang="scss">

</style>