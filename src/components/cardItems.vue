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