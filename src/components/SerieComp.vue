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
    <img :src="`//image.tmdb.org/t/p/w500${propsSerie.poster_path}`" alt="copertina"> 
    <div id="info" class="position-absolute d-flex justify-content-center align-items-center flex-column">
      <h4 class="mb-3">{{ propsSerie.name }}</h4>
      <img class="mb-3" :src=" `https://flagsapi.com/${up()}/flat/64.png`" alt="lingua">
      <div>
        <i class="fa-solid fa-star fa-beat mx-1" style="color: #ffee2e;" v-for="(elem, index) in Math.round(propsSerie.vote_average / 2)"></i>
        <i class="fa-solid fa-star fa-beat mx-1" v-for="(elem, index) in 5 - Math.round(propsSerie.vote_average / 2)"></i>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#card{
    //height: 300px;
    min-width: 200px;
    border: 2px solid black;
    background-color: white;
    &:hover{
    min-width: 300px;
    transition: 0.5s;
    }
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
      background-color: rgba(0, 0, 0, 0.6);
      color: white;
      opacity: 1;
      transition: 2s;
    }
     img{
       width: 30px;
       height: 30px;
     }
    }
  }
</style>