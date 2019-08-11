<template lang="html">
  <div id="character">
<h1>Character</h1>
  <ul id="detailWrapper" v-if="character !== null">
    <li>{{character.name}}</li>
    <li>{{character.species}}</li>
    <li>{{character.gender}}</li>
    <img class="img" v-if="character" :src="character.image" alt="country flag">
  </ul>

</div>


</template>

<script>
export default {
  name: 'character-info',
  props: ['character']
}
</script>

<style lang="css" scoped>
#character {
    box-sizing: border-box;
    height: 400px;
    width: 60%;
    background: #eee;
    color: #222;
    padding: 10px;
    border: 1px solid #ccc;
    margin: 0 auto;
    box-sizing: border-box;
    background: #fff;
    padding: 10px;
    height: 100%;
    border-radius: 3px;
  }


</style>
