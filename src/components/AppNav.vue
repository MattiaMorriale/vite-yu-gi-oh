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
</div>

</template>

<style lang="scss">

.nav{

    display: flex;
    justify-content: center;
    align-items: center;

    gap: 20px;

    height: 80px;

    

    padding: 0 20px;

    .box-img{
        margin-top: 50px;

        height: 250px;
        width: 250px;

        

        img{
            height: 100%;
            width: 100%;   
        }
    }
}

</style>