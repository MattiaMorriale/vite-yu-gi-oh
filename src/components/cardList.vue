<script>

    import AppNav from './AppNav.vue';

    import {store} from '../store.js';

    export default {

        name: 'cardList',

        components: {

            AppNav,

        },

        data() {
            return {
                store,
            }
        }

    }

</script>

<template>
    <AppNav></AppNav>

</template>

<style>

</style>