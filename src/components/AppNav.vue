<script>

    export default {

        name: 'AppNav'

    }

</script>

<template>

<div class="nav">
    <div class="box-img">
        <img src="../../public/yu-gi-oh.png" alt="#">
    </div>
    <h1>
        Yu-Gi-Oh Api
    </h1>
</div>

</template>

<style lang="scss">

.nav{

    display: flex;
    align-items: center;

    gap: 20px;

    background-color: white;

    padding: 0 20px;

    .box-img{
        height: 80px;
        width: 80px;

        img{
            height: 100%;
            width: 100%;
        }
    }

    h1{
        color: black;

        font-family: sans-serif;
        font-weight: lighter;

        font-size: 35px;
    }
}

</style>