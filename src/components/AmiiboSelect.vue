<template lang="html">
  <div><br><br>
    <select v-on:change="handleSelect" v-model="selectedAmiibo">
      <option v-for="amiibo in amiibos" v-bind:key="amiibo.id" :value="amiibo">{{amiibos.amiibo}}</option> <!-- cannot figure out why this does not return the list of amiibo names :( )-->
    </select>
  </div>

</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'amiibo-select',
  props: ['amiibos'],
  data(){
    return{
      "selectedAmiibo": null
    }
  },
  methods: {
    handleSelect(){
      // console.log(this.selectedAmiibo);
      eventBus.$emit('amiibo-selected', this.selectedAmiibo)
    }
  }
}
</script>



<style lang="css" scoped>


</style>
