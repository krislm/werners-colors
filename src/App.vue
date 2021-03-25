<template>
  <div id="app">
    <div class="top-bar flex items-center">
      <img alt="Werner's colors" src="./assets/swatches.jpg" class="logo">
      <h1>WERNER'S NOMENCLATURE OF COLOUR</h1>
    </div>
    <div class="content">
      <div class="flex justify-center">
        <Input type="text" @callback="onSearch" />
      </div>
      <div class="color-grid">
        <div v-for="(data, index) in $options.colors" :key="index" class="flex justify-center items-center">
          <ColorTile :colorCode="index" :label="data"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ColorTile from '@/components/ColorTile';
import Input from '@/components/Input';
import ColorMap from './color-map.json';

export default {
  name: 'App',
  components: {
    ColorTile,
    Input
  },
  methods: {
    onSearch: (term) => {
      if (term.length > 2) {
        console.log('search', term)
      }
    }
  },
  colors: ColorMap
}
</script>

<style>
  body {
    margin: 0;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    height: 100vh;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: min-content 1fr;
    grid-template-areas:
      "top-bar"
      "content";
  }
  .top-bar {
    background-color: #ebe4cf;
    padding: 0 30px;
  }
  .top-bar h1 {
    margin-left: 20px;
  }
  .logo {
    width: 60px;
    height: 60px;
  }
  .content {
    padding: 30px;
    background-color: #2c3e50;
  }
  .flex {
    display: flex;
  }
  .flex.justify-center {
    justify-content: center;
  }
  .flex.items-center {
    align-items: center;
  }
  .color-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
  }
</style>
