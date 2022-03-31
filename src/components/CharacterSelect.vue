<template>
  <div v-if="characters">
    <!-- inside div is character box - Should contain IMG / Name / Class -->
    <div></div>
  </div>
</template>

<script>
export default {
  name: 'CharacterSelect',
  data() {
    return {
      characters: null,
    }
  },
  computed: {
    // listCharacters() {
    //   if (this.characters < this.characters.length) {
    //     // create character block
    //   }
    //   return something;
    // }
  },
  mounted() {
    this.getCharacters();
  },
  methods: {
    getCharacters()  {
      fetch('http://localhost:5000/character')
        .then(res => res.json())
        .then(characters => {
          this.characters = characters;
        });
    }
  }
}
</script>

<style scoped>
li {
  list-style: none;
}
</style>