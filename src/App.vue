<template>
  <character-list />
</template>

<script>
import characterList from './views/CharacterList/index.vue'

export default {
  name: 'App',
  components: {
    characterList
  }
}
</script>

<style>
  @import './assets/styles/index.css';
</style>
