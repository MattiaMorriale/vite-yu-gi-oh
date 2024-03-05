<script>

    import axios from 'axios';

    import cardItems from './cardItems.vue';

    import callCardSelect from './callCardSelect.vue';

    import {store} from '../store.js';

    export default {

        name: 'AppMain',

        components: {

            cardItems,
            callCardSelect,

        },

        data() {
            return {

                store,

            }
        },
 
        methods: {

            searcharchetypes () {

            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=1000&offset=0&archetype=' + this.store.arch_selected)
                .then(res => {

                this.store.card = res.data.data;
                });
            },
        }
    }

</script>

<template>

    <div class="container">

        <div class="box-card">

            <callCardSelect @search="searcharchetypes()"></callCardSelect>

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