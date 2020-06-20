<template lang="html">
  <div v-if="character">
    <h3>{{character.name}}</h3>
    <img :src="character.image" alt="character-image" height="400">
  </div>
</template>

<script>

import {eventBus} from './components/CharacterSelect.vue'
export default {
  name: 'character-detail',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
