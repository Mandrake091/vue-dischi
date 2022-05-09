<template>
<section> 
    <app-loader v-if="loading"/>
 
   <app-select @performSearch="mySearch" :genreList="genre" :authorsList="authors"/>
    <div class="row w-75 justify-content-center py-4 m-auto">
        
        <div class="col-12 col-sm-4 col-md-3 col-lg-2 p-0"
        v-for="(album, index) in filteredAlbumList" :key="index">
        <app-card :item="album"/>
        </div>
    </div>
</section>
  
</template>

<script>
import axios from 'axios';
import AppCard from './AppCard.vue'
import AppLoader from './AppLoader.vue';
import AppSelect from './AppSelect.vue';

export default {
    name: "AppGrid",
    components: { AppCard, AppLoader, AppSelect },
    data(){
        return {
            albumList:[],
            api:'https://flynn.boolean.careers/exercises/api/array/music',
            loading:false,
            genre:[],
            authors:[],
            searchText:"",
            mergedArray:[],
        
        
        }
    },
    methods:{
 
        mySearch(text){
            this.loading=true
        setTimeout(()=>{
               this.searchText = text; 
               this.loading=false
            },1000)
        }  
    },
       computed:{
        filteredAlbumList(){
            if (this.searchText === '') {
                return this.albumList;
        }
        return this.albumList.filter((item)=>{
            return item.author === this.searchText || item.genre === this.searchText
        })
       }},
    created(){
        this.loading = true;
        setTimeout(()=>{
            this.loading = false
            axios.get(this.api).then((res)=>{
            this.albumList = res.data.response;
            this.albumList.forEach((el)=>{
                if(!this.genre.includes(el.genre)){
                    this.genre.push(el.genre)
                }else if (!this.authors.includes(el.author)){
                    this.authors.push(el.author)
                }
                this.mergedArray= [...this.genre, ...this.authors]   
            })
            console.log(this.albumList)
            console.log(this.genre)
            console.log(this.authors)
            console.log(this.mergedArray)
        }).catch((error) => {
            console.log(error)
        }) 
        },1000)
    },    
 
}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/general.scss";

.row{
    column-gap: 20px;
    row-gap: 20px;
}

</style>