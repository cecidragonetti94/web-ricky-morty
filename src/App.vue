

  
<template>
  <div class="container">
    <h1>Rick And Morty</h1>

    <FilterByStatus />
    <FilterByName />
    <ListCharacters />
  </div>
</template>

<script>
import ListCharacters from "./components/ListCharacter.vue";
import FilterByStatus from "./components/FilterByStatus.vue";
import FilterByName from "./components/FilterByName.vue";
export default {
  name: "App",
  components: {
    ListCharacters,
    FilterByStatus,
    FilterByName,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Shadows+Into+Light&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Manrope:wght@200&family=Shadows+Into+Light&display=swap");
* {
  height: auto;
  width: 100%;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {

  background-color: rgb(78, 76, 76);
  color: blanchedalmond;
  font-family: "Manrope", sans-serif;
  overflow-x: hidden;
}
h1 {
  font-family: "Shadows Into Light", cursive;
  color: rgb(48, 206, 82);
  font-size: 40px;
  text-align: center;
}
</style>
