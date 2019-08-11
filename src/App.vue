<template lang="html">
  <div>
  <character-select :characters='characters'/>
  <character-info :character='selectedCharacter'/>
</div>


</template>

<script>
import { eventBus } from './main.js'
import CharacterSelect from './components/CharacterSelect.vue'
import CharacterInfo from './components/CharacterInfo.vue'

export default {
  name: 'app',
  components: {
    'character-select': CharacterSelect,
    'character-info': CharacterInfo
  },
  data() {
    return {
      characters: [],
      selectedCharacter: null
    }
  },
  mounted() {


    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => characters=characters.results)
    .then(characters => this.characters=characters)

  eventBus.$on('character-selected', (SelectedIndex) => {
    this.selectedCharacter = this.characters[SelectedIndex];
  })
},
}
</script>

<style lang="css" scoped>
</style>
