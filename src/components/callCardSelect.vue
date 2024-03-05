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

    <select id="select" v-model="store.arch_selected" @click="$emit('search')">

        <option  value="">Scegli il tuo Archetipo</option>
        <option :value="currentArc.archetype_name" v-for="currentArc in store.archetype">{{ currentArc.archetype_name }}</option>

    </select>

</template>

<style>

#select{

    background-color: white;
    color: black;

    padding: 8px 12px;

    margin: 30px 0 30px 8px;

    border-radius: 5px;

}

</style>