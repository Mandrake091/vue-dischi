<template>
<section>
    <app-loader v-if="loading"/>
    <div class="row w-75 justify-content-center py-5 m-auto">
        <div class="col-12 col-sm-4 col-md-3 col-lg-2 p-0"
        v-for="(album, index) in albumList" :key="index">
        <app-card :item="album"/>
        </div>
    </div>
</section>
  
</template>

<script>
import axios from 'axios';
import AppCard from './AppCard.vue'
import AppLoader from './AppLoader.vue';

export default {
    name: "AppGrid",
    components: { AppCard, AppLoader },
    data(){
        return {
            albumList:[],
            api:'https://flynn.boolean.careers/exercises/api/array/music',
            loading:false
        }
    },
    mounted(){
        this.loading = true;
        setTimeout(()=>{
            axios.get(this.api).then((res)=>{
            this.albumList = res.data.response;
            this.loading = false
            console.log(this.albumList)
        }).catch((error) => {
            console.log(error)
        }) 
        },1000)
    }    
}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/general.scss";

.row{
    column-gap: 20px;
    row-gap: 20px;
}

</style>