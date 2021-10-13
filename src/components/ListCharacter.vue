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
  grid-template-columns: 550px 550px 500px;
	grid-template-rows: repeat(7, 250px);
  margin-left: 8px;

} 
@media screen and (min-width:450px){
  .characters{
display: grid;
  grid-template-columns: 384px;
	grid-template-rows: repeat(1, 250px);
  margin-left: 8px;
  }
}
@media screen and (min-width: 700px){
  .characters{
 display: grid;
  grid-template-columns: 350px 350px;
	grid-template-rows: repeat(7, 250px);
  margin-left: 8px;
  font-size:15px;

}
}
@media screen and (min-width: 1000px){
  .characters{
 display: grid;
  grid-template-columns: 384px 384px 384px;
	grid-template-rows: repeat(7, 250px);
  margin-left: 8px;
  font-size:15px;

}
}
@media screen and (min-width: 1200px){
  .characters{
 display: grid;
  grid-template-columns: 450px 450px 430px;
	grid-template-rows: repeat(7, 250px);
  margin-left: 8px;


}
}
@media screen and (min-width: 1500px){
  .characters{
 display: grid;
  grid-template-columns: 600px 600px 500px;
	grid-template-rows: repeat(7, 250px);
  margin-left: 8px;


}
}


</style>