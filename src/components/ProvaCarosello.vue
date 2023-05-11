<script>
import {store} from '../store'

export default{
    name:"ProvaCarosello",
    components:{
        
    },
    data(){
        return{
            store
        }
    }
}
</script>

<template>
<div id="carouselExampleInterval" class="carousel slide w-100 h-100" data-bs-ride="carousel">
    <div class="carousel-inner">
        <div class="carousel-item active" data-bs-interval="3000">
            <div class="d-flex justify-content-around">
                <img src="https://th.bing.com/th/id/OIP.td2k8pIQXdkrwHJy5wdjHwHaE6?w=266&h=180&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
                <img src="https://th.bing.com/th/id/OIP.MwaDkAcfHgW6oPZAQR6-TAAAAA?w=221&h=180&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
                <img src="https://th.bing.com/th/id/OIP.tbrC7Q2_NS61uH_fHjfFAgHaEs?w=301&h=190&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
            </div>
        </div>
        <div class="carousel-item active" data-bs-interval="3000">
            <div class="d-flex justify-content-around">
                <img src="https://th.bing.com/th/id/OIP.lvV6j1Z54ipww0ldhrDu_wHaFj?w=267&h=200&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
                <img src="data:image/jpeg;base64,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" class="d-block w-25" alt="Attore">
                <img src="https://th.bing.com/th/id/OIP.2HZVlVz75w0Y6yqz3dGbsQHaF6?w=269&h=215&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
            </div>
        </div>
        <div class="carousel-item active" data-bs-interval="3000">
            <div class="d-flex justify-content-around">
                <img src="https://th.bing.com/th/id/OIP.iP3W62r00nJf-8keciVuqgHaF7?w=269&h=215&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
                <img src="https://th.bing.com/th/id/OIP.wx2RudyNTw52bJshc4_m8QHaE7?w=270&h=180&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
                <img src="https://th.bing.com/th/id/OIP.XLFBYco0dFIh-sbV3jZT-QHaEK?w=283&h=180&c=7&r=0&o=5&pid=1.7" class="d-block w-25" alt="Attore">
            </div>
        </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleInterval" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
    </button>
     <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleInterval" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
    </button>
</div>

</template>

<style lang="scss" scoped>

</style>