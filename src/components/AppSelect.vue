<template>
 <select 
 class="form-select form-select-sm h-75 w-25 text-center m-auto mt-4" aria-label=".form-select-sm example"
 @change="changeSelect"
 v-model="inputText"
 >
  <option value="">Filter by genre</option>
  <option :value="generi" 
  v-for="(generi, index) in genreList"  :key="index">{{generi}}</option>
</select>
</template>

<script>
export default {
    name:'AppSelect',
    data(){
        return {
            inputText:""
        }
    },
    props:['genreList'],

    methods:{
        changeSelect(){
            this.$emit("performSearch", this.inputText)
        }
    }
}
</script>

<style>

</style>