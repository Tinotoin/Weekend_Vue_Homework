<template>
  <div id="app">
    <amiibo-select :amiibos="amiibos"></amiibo-select>
    <!-- <amiibo-detail :amiibo-detail="amiibo-detail"></amiibo-detail> -->

    <div id="input">
    <label for="new-amiibo" name="amiibo">Add a new amiibo!</label>
    <input v-model="newAmiibo"  name="amiibo">
    <button type="submit" name="amiibo">amiibo, awaayy!</button>
    <p>You created {{newAmiibo}}</p>
  </div>


  </div>




</template>

<script>

import { eventBus } from './main.js'
import amiiboSelect from './components/AmiiboSelect.vue'
// import amiiboDetail from './components/AmiiboDetail.vue'
export default {
  name: 'App',
  data(){
    return{
      amiibos: [],
      selectedAmiibo: null,
      newAmiibo: ""

// Was struggling with adding items - this method isn't correct.

    // };
    //   methods: {
    //   newAmiibo: function(amiibo){
    //     this.amiibo.push({
    //       name: this.newAmiibo,
    //     })
    //     this.newItem = "";


    };
  },
mounted(){
  fetch("https://www.amiiboapi.com/api/amiibo/")
  .then(res => res.json())
  .then(data => this.amiibos = data)

  eventBus.$on('amiibo-selected', (amiibo) => {
    this.selectedAmiibo = amiibo
  })
},

  components: {
    "amiibo-select": amiiboSelect,
    // 'amiibo-detail': amiiboDetail
    // "new-amiibo": newAmiibo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  background-image: url("./assets/amiibo_bg.jpg");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
}

input {
  background-color: gold;
}

p {
  background-color: silver;
  flex-wrap: wrap;
}
</style>
