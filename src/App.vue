<template>
  <div id="app">
    <character-select :characters="characters"></character-select>
    <!-- <character-detail :character-detail="character-detail"></character-detail> -->
  </div>
</template>

<script>

import { eventBus } from './main.js'
import CharacterSelect from './components/CharacterSelect.vue'
// import CharacterDetail from './components/CharacterDetail.vue'
export default {
  name: 'App',
  data(){
    return{
      characters: [],
      selectedCharacter: null
    }
  },
mounted(){
  fetch('https://rickandmortyapi.com/api/character/')
  .then(res => res.json())
  .then(data => this.characters = data)

  eventBus.$on('character-selected', (character) => {
    this.selectedCharacter = character
  })
},

  components: {
    'character-select': CharacterSelect,
    // 'character-detail': CharacterDetail
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
</style>
