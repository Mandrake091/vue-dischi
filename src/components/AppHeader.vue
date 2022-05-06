<template>
    <header>
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
}
</style>