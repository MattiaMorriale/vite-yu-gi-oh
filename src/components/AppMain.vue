<script>

    import cardItems from './cardItems.vue';

    import {store} from '../store.js';

    export default {

        name: 'AppMain',

        components: {

            cardItems,

        },

        data() {
            return {

                store,

            }
        }

    }

</script>

<template>

    <div class="container">

        <div class="box-card">

            <select id="select">
                <option value="Alien">Alien</option>
                <option value="Weapon">Weapon</option>
                <option value="Poison">Poison</option>
            </select>

            <div class="card-container">
                <div class="found">
                    <strong>found {{ store.card.length }} cards </strong>
                </div>
                <cardItems v-for="currentCard in store.card" :card="currentCard"></cardItems>
            </div>

        </div>

    </div>

</template>

<style lang="scss">

.container{
    width: 100%;

    background-color: #d48f38;

    display: flex;
    justify-content: center;
    

    .box-card{

        width: 83%;

        #select{
            background-color: white;
            color: black;
    
            padding: 8px 12px;

            margin: 30px 0 30px 8px;
    
            border-radius: 5px;
        }

        .card-container{
            width: 100%;

            display: flex;
            flex-wrap: wrap;

            gap: 25px;

            padding: 50px;
            margin-bottom: 80px;

            background-color: white;

            .found{
                width: 100%;
                height: 80px;

                background-color: #333;

                display: flex;
                align-items: center;

                strong{
                    color: white;

                    padding-left: 20px;

                    font-size: 25px;
                }
            }
        }

    }

}



</style>