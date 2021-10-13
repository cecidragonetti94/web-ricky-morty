<template>
  <section>
    <div class="characters">
      <div class="characters__item" v-for="character in characters" :key="character.id">
        <CardCharacter :character="character" />
      </div>
    </div>
  </section>
</template>

<script>
import { computed, onMounted } from 'vue'
import { useStore } from 'vuex'
import CardCharacter from './CardCharacter.vue'

export default {
  name: 'Characters',
  components: {
    CardCharacter,
  },
  setup() {
    const store = useStore()
    const characters = computed(() => {
      return store.state.charactersFilter
    })
    onMounted(() => {
      store.dispatch('getCharacters')
    })
    return {
      characters
    }
  }
}
</script>

<style>
.characters{
  display: grid;
  grid-template-columns: 550px 550px 550px;
	grid-template-rows: repeat(7, 250px);
  margin-left: 8px;

}

</style>