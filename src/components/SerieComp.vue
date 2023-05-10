<script>
import {store} from '../store/'

export default{
  name: "SerieComp",
  props: ['propsSerie'],
    data(){
      return{
        store
      }
    },
     created(){
      this.up()
    },
    methods:{
      up(){
        let lingua = this.propsSerie.original_language
        if(lingua=='en'){
          lingua='gb'
        }
        else if(lingua=='ja'){
          lingua='jp'
        }
        else if(lingua=='zh'){
          lingua='cn'
        }
        let bandiera = lingua.toUpperCase()
        return bandiera
      }
    }   
  }
</script>

<template>
  <div id="card" class="mx-2 text-center position-relative">
    <img :src="`//image.tmdb.org/t/p/w342${propsSerie.poster_path}`" alt="copertina"> 
    <div id="info" class="position-absolute d-flex justify-content-center align-items-center flex-column">
      <h4>{{ propsSerie.name }}</h4>
      <img :src=" `https://flagsapi.com/${up()}/flat/64.png`" alt="lingua">
      <h6>{{ propsSerie.vote_average }}</h6>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#card{
    height: 300px;
    min-width: 200px;
    border: 2px solid black;
    background-color: white;
    img{
      width: 100%;
      height: 100%;
    }
     #info{
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      opacity: 0;
    &:hover{
      background-color: rgba(0, 0, 0, 0.5);
      color: white;
      opacity: 1;
    }
     img{
       width: 30px;
       height: 30px;
     }
    }
  }
</style>