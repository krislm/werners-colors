<template>
  <div class="input flex">
    <label>
      <input :type="type"  @input="addEvent" @change="addEvent">
    </label>
    <SearchIcon />
  </div>
</template>

<script>
import SearchIcon from '@/assets/SearchIcon';

export default {
  name: 'Input',
  props: {
    type: String,
    callback: Function
  },
  components: {
    SearchIcon
  },
  methods: {
    addEvent ({ target }) {
      this.$emit('callback', target.value)
    },
  }
}
</script>

<style scoped>
  .input {
    padding: 8px 16px;
    background-color: #f7f7f7;
    border-radius: 6px;
  }

  input {
    background: transparent;
    border: none;
    font-size: 16px;
    padding: 0;
  }
  input:focus {
    outline-style: none;
  }
</style>