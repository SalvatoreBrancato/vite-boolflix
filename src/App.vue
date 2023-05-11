<script>
import MainComp from './components/MainComp.vue';
import NavComp from './components/NavComp.vue';
import {store} from './store';
import axios from 'axios';

export default{
  name: "App",
  components:{
    NavComp,
    MainComp
},data(){
  return{
    store
  }
},
created(){
  this.chiamataApi()
},
methods:{
  chiamataHome(){
    
      axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=0487d30568617584a3cc3c09136753c9&language=it-IT`)
      .then((res)=>{
        const datiApi = res.data.results
        store.arrayNetflix = datiApi
        
      })
      axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=0487d30568617584a3cc3c09136753c9&language=it-IT`)
      .then((res)=>{
        const datiApiSerie = res.data.results
        store.arraySerie = datiApiSerie
      })

    },

  chiamataApi(){
    if(store.testoRicerca == ""){
      axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=0487d30568617584a3cc3c09136753c9&language=it-IT`)
      .then((res)=>{
        const datiApi = res.data.results
        store.arrayNetflix = datiApi
        
      })
      axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=0487d30568617584a3cc3c09136753c9&language=it-IT`)
      .then((res)=>{
        const datiApiSerie = res.data.results
        store.arraySerie = datiApiSerie
      })
    } else{
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=0487d30568617584a3cc3c09136753c9&language=it-IT&query=${store.testoRicerca}`)
      .then((res)=>{
        const datiApi = res.data.results
        store.arrayNetflix = datiApi
        store.testoRicerca = ""
        
      })
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=0487d30568617584a3cc3c09136753c9&language=it-IT&query=${store.testoRicerca}`)
      .then((res)=>{
        const datiApiSerie = res.data.results
        store.arraySerie = datiApiSerie
        store.testoRicerca = ""
      })
    }
  }
}
}
</script>

<template>
  <NavComp @emitRicerca="chiamataApi" @emitHome="chiamataHome"/>
  <MainComp/>
</template>

<style lang="scss">
@use "./style/main.scss";
</style>
