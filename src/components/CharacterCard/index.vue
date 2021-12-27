<template>
  <div class='character-card'>
    <img :src='character.image' class='card-image' />
    <h4>{{ character.name }}</h4>

    <div class='card-info'>
      <div class='info-item'>
        <span>{{ character.species }}</span>
      </div>

      <div class='info-item'>
        <span>{{ character.gender }}</span>
      </div>
    </div>
  </div>
</template>

<style>
@import './style.css'
</style>

<script>
export default {
  name: 'character-card',
  components: {},
  props: ['character'],
}
</script>