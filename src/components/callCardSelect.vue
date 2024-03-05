<script>

    import {store} from '../store.js';

    export default {

        name: 'callCardSelect',

        data() {
            return {

                store,

            }
        }

    }

</script>

<template>

    <select id="select" v-model="store.arch_selected" @change="$emit('search')">

        <option  value="">Scegli il tuo Archetipo</option>
        <option :value="currentArc.archetype_name" v-for="currentArc in store.archetype">{{ currentArc.archetype_name }}</option>

    </select>

</template>

<style>

#select{

    background-color: rgb(3, 22, 65);
    color: goldenrod;

    padding: 8px 12px;

    margin: 30px 0 30px 8px;

    border-radius: 5px;

    box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;

    border: 4px solid goldenrod;

    position: relative;

}

</style>