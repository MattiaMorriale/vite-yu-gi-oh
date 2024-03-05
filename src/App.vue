<script>

  import axios from 'axios';

  import {store} from './store.js';

  import cardList from './components/cardList.vue';

  export default {

    data() {
      return {

        store,

        isLoading: true,

      }
    },

    created() {

      axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=1000&offset=0')

        .then(res => {

          console.log(res.data.data)

          this.store.card = res.data.data

          this.isLoading = false

        }).catch(err => {

          console.log(err)

        })

      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(res => {

        this.store.archetype = res.data;
        });
    },
    
    components: {

      cardList,
      
    },

  };



</script>

<template>

  <div class="box-loader" v-if="isLoading">
    <div class="loader"></div>
  </div>
  <cardList></cardList>

</template>

<style lang="scss">

.box-loader{

  position: sticky;
  width: 100%;
  height: 100vh;

  display: flex;
  align-items: center;
  justify-content: center;

  z-index: 99;

  background-color: #333;

.loader {
  width: fit-content;
  font-weight: bold;
  font-family: sans-serif;
  font-size: 50px;
  padding-bottom: 8px;
  background: linear-gradient(currentColor 0 0) 0 100%/0% 3px no-repeat;
  animation: l2 2s linear infinite;
}
.loader:before {
  content:"Loading..."
}
@keyframes l2 {to{background-size: 100% 3px}}

}


</style>
