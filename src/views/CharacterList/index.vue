<template>
  <span
    v-if='isLoading == true'>Carregando</span>

  <div
    class='character-list-container'
    v-if='isLoading == false'>
    <character-card
      v-for='character in characterList'
      :key="character.id"
      :character="character" />
  </div>
</template>

<script>
// Third party
import axios from 'axios'

// Project
import CharacterCard from '../../components/CharacterCard/index.vue'

export default {
  name: 'character-list',
  data: function() {
    return {
      characterList: [],
      isLoading: false,
      prevPage: null,
      nextPage: null
    }
  },
  created: function () {
    this.isLoading = true

    axios
      .get('https://rickandmortyapi.com/api/character')
      .then((response) => {
        const { results, prev, next } = response.data
        this.characterList = results
        this.prevPage = prev
        this.nextPage = next
        this.isLoading = false
      })
  },
  components: {
    CharacterCard
  }
}
</script>

<style>
@import './style.css'
</style>