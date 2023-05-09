<script>
import MainComp from './components/MainComp.vue';
import NavComp from './components/NavComp.vue';
import {store} from './store'

export default{
  name: "App",
  components:{
    NavComp,
    MainComp
},data(){
  return{
    store
  }
}

}
</script>

<template>
  <NavComp/>
  <MainComp/>
</template>

<style lang="scss">
@use "./style/main.scss";
</style>
