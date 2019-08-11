<template lang="html">
  <select @change='characterSelected'>
  <option selected disabled></option>
  <option v-for='(character, index) in characters' :value='index'>{{character.name}}</option>
</select>

</template>

<script>
import { eventBus } from '@/main.js'

export default {
  name: 'character-select',
  props: ['characters'],
  methods: {
    characterSelected(e) {
      const SelectedIndex = e.target.value;
      eventBus.$emit('character-selected', SelectedIndex);
     }
  }
}
</script>

<style lang="css" scoped>
</style>
