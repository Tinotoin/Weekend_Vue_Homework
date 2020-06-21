<template lang="html">
  <div v-if="amiibo">
    <h3>{{amiibos.amiibo.name}}</h3> <!-- cannot figure out why this does not return the list of amiibo names :( )-->
    <!-- <img :src="amiibo.image" alt="amiibo-image" height="400"> -->
  </div>
</template>

<script>

export default {
  name: 'amiibo-detail',
  props: ['amiibo']
}
</script>

<style lang="css" scoped>
</style>
