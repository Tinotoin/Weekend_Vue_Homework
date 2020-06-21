<template lang="html">
  <div class="amiibolistitem">
    <p>{{amiibos.amiibo.name}}</p>


  </div>

</template>

<script>

import { eventBus } from "./main.js";

export default {
  name: "amiibo-list-item",
  props: ["amiibo"],
  data:
},

methods: {
  displayInfo: function() {
    eventBus.$emit("amiibo-selected", this.amiibo);
    saveNewItem: function(){
      this.items.push({
        name: this.newAmiibo,
      })
      this.newItem = "";
    },
};

</script>

<style lang="css" scoped>
</style>
