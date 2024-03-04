<script>

  import axios from 'axios';

  import {store} from './store.js';

  import cardList from './components/cardList.vue';

  export default {

    data() {
      return {

        store,

      }
    },

    created() {

      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')

        .then(res => {

          console.log(res.data.data)

          this.store.cards = res.data.data

        }).catch(err => {

          console.log(err)

        })

    },
    
    components: {

      cardList,
      
    },

  };



</script>

<template>

  <cardList></cardList>

</template>

<style >

</style>
