<template>
    <header class="d-flex justify-content-between align-items-center">
        <img class="py-2" src="/images/logo.png" alt="">
        
    </header>
</template>

<script>
export default {
    name: "AppHeader"
}
</script>

<style lang="scss" scoped>
@import "../assets/style/general.scss";

img{
   height: 100%;
}
header{
    background-color: $bg-navbar;
    height: 50px;
    box-shadow: 5px 10px 20px #0000006b;
}
</style>