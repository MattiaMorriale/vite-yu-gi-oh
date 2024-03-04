<script>

    import AppNav from './AppNav.vue';

    import AppMain from './AppMain.vue';

    import {store} from '../store.js';

    export default {

        name: 'cardList',

        components: {

            AppNav,
            AppMain,

        },

        

    }

</script>

<template>

    <AppNav></AppNav>

    <AppMain></AppMain>

</template>

<style>

</style>