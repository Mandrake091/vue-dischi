<template>
<div>
    <img class="img-fluid" :src="item.poster" alt="">
    <h4 class="fs-5 text-center fw-bold">{{item.title}}</h4>
    <p>{{item.author}}</p>
    <p>{{item.year}}</p>
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
div{
    color: $bg-color;
    background-color: $bg-navbar;
}
p{
    text-align: center;
}

</style>