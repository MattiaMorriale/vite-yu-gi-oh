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
                <div class="card-container-in">

                    <div class="square">•</div>
                    <div class="square">•</div>
                    <div class="square">•</div>
                    <div class="square">•</div>
                    
                    <div class="found">
                        <strong>Found {{ store.card.length }} {{ store.arch_selected }} Cards</strong>
                    </div>
                    <cardItems v-for="currentCard in store.card" :card="currentCard"></cardItems>


                </div>

            </div>

        </div>

    </div>

</template>

<style lang="scss">

.container{
    width: 100%;

    display: flex;
    justify-content: center;
    

    .box-card{

        width: 83%;

        .card-container{
            width: 100%;

            padding: 5px;
            margin-bottom: 80px;

            background-color: rgb(3, 22, 65);

            border: 4px solid goldenrod;

            .card-container-in{

                width: 100%;

                display: flex;
                flex-wrap: wrap;

                padding: 50px;

                gap: 25px;

                border: 4px solid goldenrod;

                position: relative;

                .square{
                    display: flex;
                    align-items: center;
                    justify-content: center;

                    font-size: 20px;

                    color: goldenrod;
                    
                    height: 20px;
                    width: 20px;

                    position: absolute;

                    border: 4px solid goldenrod;
                    
                }

                .square:nth-of-type(1) {
                    top: 0;
                    left: 0;

                    border-top: none;
                    border-left: none;
                }

                .square:nth-of-type(2) {
                    top: 0;
                    right: 0;

                    border-top: none;
                    border-right: none;
                }

                .square:nth-of-type(3) {
                    bottom: 0;
                    left: 0;

                    border-bottom: none;
                    border-left: none;
                }

                .square:nth-of-type(4) {
                    bottom: 0;
                    right: 0;

                    border-bottom: none;
                    border-right: none;
                }

                .found{
                    width: 100%;
                    height: 80px;
    
                    background-color: #333;
    
                    display: flex;
                    align-items: center;

                    border: 4px solid goldenrod;

                    box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset, rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset, rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px, rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px, rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;
    
                    strong{
                        color: white;
    
                        padding-left: 20px;
    
                        font-size: 25px;
                    }
                }

            }

        }

    }

}



</style>