<template>
  <div
      class="color-tile"
      v-bind:style="{
        backgroundImage: 'url(../../colors/'+colorCode+'-'+label.toLowerCase().split(' ').join('-')+'.jpg)'
      }">
    <p>{{label}}</p>
  </div>
</template>

<script>
export default {
  name: 'ColorTile',
  props: {
    colorCode: String,
    label: String
  },
}
</script>

<style scoped>
  .color-tile {
    width: 60px;
    height: 60px;
    border-radius: 10px;
  }
</style>