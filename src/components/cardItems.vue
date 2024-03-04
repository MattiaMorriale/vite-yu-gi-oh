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

    border: black solid 1px;

    box-shadow: rgb(38, 57, 77) 0px 20px 30px -10px;

    img{
        width: 100%;
    }

    .text-box{

        height: 100px;
        width: 100%;

        display: flex;
        justify-content: center;
        align-items: center;

        flex-direction: column;

        border-top: solid black 1px;



        background-color: #d48f38;

        strong{
            text-align: center;
        }

        p{
            color: black;
        }

    }

    
}

</style>