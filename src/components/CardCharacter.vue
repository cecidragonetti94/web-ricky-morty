<template>
  <div class="character">
    <img :src="character.image" :alt="character.name">
    <div class="character__info">
      <h3>{{ character.name }}</h3>
      <div class="status">
        <span
          :class="
            character.status == 'Alive' ? 'alive' :
            character.status == 'Dead' ? 'dead' :
            'default'"
        ></span>
        <span>{{ character.status }} - {{ character.species }}</span>
      </div>
      <div class="origen">
        <span>
          Origin: 
          {{ character.origin.name }}
        </span>
      </div>
      <div class="location">
        <span>
          Location: 
          {{ character.location.name }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['character']
}
</script>

<style >
img{
  width: 200px;
  height: 200px;
}
.character{
 font-size: 12px;
 margin: 5px 5px;
 border: 1px solid rgb(48, 206, 82);
 box-sizing: border-box;
display: flex;
flex-direction: column;


}
@media screen and (min-width: 485px){

 .character{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 100px 100px;
    background-color: rgb(78, 76, 76);
    font-size: 20px;

  }
}
</style>