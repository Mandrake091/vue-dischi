<template>
<div class="col text-center h-100 d-flex flex-column align-items-center justify-content-between">
    <div>
     <img class="w-100 p-1" :src="item.poster" alt="">
    <h4 class="text-center fw-bold p-2 text-uppercase">{{item.title}}</h4>   
    </div>
    <div>
        <p class="px-2 m-0">{{item.author}}</p>
        <p class="px-2">{{item.year}}</p>    
    </div>
   
</div>
  
</template>

<script>
export default {
    name: "AppCard",
    props:{
        item:Object
    }
}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/general.scss";

.col{
    min-width: 150px;
    box-shadow: 5px 10px 20px #0000006b;
}
div{
    overflow: hidden;
    color: $bg-color;
    background-color: $bg-navbar;
   
}
h4{
    font-size: $main-font-size;
    text-overflow: ellipsis;
}
p{
    color: $text-secondary;
    font-size: $small-font-size;
}
</style>