<template>

    <div class="container">
        <div class="row pt-4 justify-content-center align-items-center">
            <div class="col-6 col-md-4 col-lg-3 col-xl-2">
                <select 
 class="form-select form-select-sm text-center m-auto" aria-label=".form-select-sm example"
 @change="changeSelect"
 v-model="inputText"
 >
  <option value="">Filter by Author</option>
  <option :value="authors" 
  v-for="(authors, index) in authorsList" :key="index">{{authors}}</option>
</select>
            </div>
            <div class="col-6 col-md-4 col-lg-3 col-xl-2">
                <select 
 class="form-select form-select-sm text-center m-auto" aria-label=".form-select-sm example"
 @change="changeSelect"
 v-model="inputText"
 >
  <option value="">Filter by Genre</option>
  <option :value="generi" 
  v-for="(generi, index) in genreList" :key="index">{{generi}}</option>
</select>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'AppSelect',
    data(){
        return {
            inputText:""
        }
    },
    props:['genreList', 'authorsList'],
   
    methods:{      
        changeSelect(){
            this.$emit("performSearch", this.inputText)
            console.log(this.inputText)
        }
    }
}
</script>

<style>

</style>