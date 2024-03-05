<script>

    export default {

        name: 'cardItems',

        props: {

            card: Object,

        },

    }

</script>

<template>
    <div class="container-card">
        <img :src="card.card_images[0].image_url_small" alt="@">
        <div class="text-box">
            <strong class="name">{{ card.name }}</strong>
            <p class="type">{{ card.archetype }}</p>
        </div>
    </div>

</template>

<style>

.container-card{
    width: calc(100% / 5 - 25px / 5 * 4);

    display: flex;
    flex-direction: column;
    align-items: flex-start;

    box-shadow: rgb(38, 57, 77) 0px 20px 30px -10px;

    img{
        width: 100%;

        border: 4px solid goldenrod;
    }

    .text-box{

        height: 100px;
        width: 100%;

        display: flex;
        justify-content: center;
        align-items: center;

        flex-direction: column;

        border: solid goldenrod 4px;
        border-top: solid goldenrod 1px;
        
        border-bottom-left-radius: 15px;
        border-bottom-right-radius: 15px;



        background-color: goldenrod;

        box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset, rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset, rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px, rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px, rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;

        strong{
            text-align: center;
        }

        p{
            color: black;
        }

    }

    
}

</style>