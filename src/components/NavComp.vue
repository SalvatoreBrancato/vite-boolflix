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
            <span class="px-2" @click="$emit(`emitHome`)">Home</span>
            <span class="px-2">Film</span>
            <span class="px-2">Serie</span>
        </div>
        <div class="w-50">
            <input @keyup.enter="$emit('emitRicerca')" type="text" v-model="store.testoRicerca" placeholder="Cerca un titolo..." class="rounded-start-pill ps-2">
            <button class="rounded-end-pill px-4" @click="$emit('emitRicerca')">
                <i class="fa-solid fa-magnifying-glass fa-beat-fade"></i>
            </button>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    #container{
        background-color: rgb(0,0,0);
        #logo{
            width: 15%;
        }
        span{
            margin-left: 10px;
            cursor: pointer;
            &:hover{
                color: red;
                border-left: 2px solid red;
            }
        }
        button{
            background-color: rgb(63, 63, 249);
            color: white;
            font-weight: bold;
        }
    }
</style>