<template lang="html">
  <div>
    <p>Rick and Morty Character Lookup</p>
    <select v-on:change="handleSelect" v-model="selectedCharacter">
      <option v-for="character in characters" v-bind:key="character.id" :value="character">{{character.name}}</option>
    </select>
  </div>

</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: 'character-select',
  props: ['characters'],
  data(){
    return{
      "selectedCharacter": null
    }
  },
  methods: {
    handleSelect(){
      eventBus.$emit('character-selected', this.selectedCharacter)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
