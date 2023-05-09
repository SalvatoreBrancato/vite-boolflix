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
    <div class="d-flex justify-content-between align-items-center bg-dark py-2">
        <div class="text-white">
            <img id="logo" src="https://th.bing.com/th/id/R.4d30a09d38e6dfe3feaa31920a680108?rik=GnWkgmKvj5nwNg&riu=http%3a%2f%2fwww.cultjer.com%2fimg%2fug_photo%2f2016_09%2f76248820160921034356.jpg&ehk=grD%2fdqb%2b43FMvO3KHmAdPwgUvOikuZkwrJQwMPdCHUM%3d&risl=&pid=ImgRaw&r=0" alt="">
        </div>
        <div class="w-25">
            <input type="text">
            <button class="ms-2 rounded-pill">Cerca</button>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
    #logo{
        width: 10%;
    }
</style>