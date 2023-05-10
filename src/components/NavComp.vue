<script>
import {store} from '../store/'
export default{
    name: "NavComp",
    data() {
        return {
            store
        };
    }
    
}
</script>

<template>
    <div id="container" class="d-flex justify-content-between align-items-center py-2">
        <div class="text-white">
            <img id="logo" src="https://th.bing.com/th/id/R.4d30a09d38e6dfe3feaa31920a680108?rik=GnWkgmKvj5nwNg&riu=http%3a%2f%2fwww.cultjer.com%2fimg%2fug_photo%2f2016_09%2f76248820160921034356.jpg&ehk=grD%2fdqb%2b43FMvO3KHmAdPwgUvOikuZkwrJQwMPdCHUM%3d&risl=&pid=ImgRaw&r=0" alt="">
        </div>
        <div class="w-25">
            <input type="text" v-model="store.testoRicerca" placeholder="Cerca un titolo...">
            <button class="ms-2 rounded-pill" @click="$emit('emitRicerca')">Cerca</button>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
    #container{
        background-color: rgb(0,0,0);
        #logo{
            width: 10%;
        }
        input{
            border-radius: 10px;
        }
        button{
            background-color: rgb(63, 63, 249);
            color: white;
            padding: 5px;
            font-weight: bold;
        }
    }
</style>