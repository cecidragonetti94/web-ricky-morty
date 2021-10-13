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
display: flex;
flex-direction: row;
 border: 3px solid rgb(16, 97, 33);
 box-sizing: border-box;
max-width: 700px;
border-radius: 5px;
align-items: center;


}
@media screen and (min-width: 485px){

 .character{
   background-color: rgb(126, 123, 123);
   font-size: 20px;
background-color: rgb(48, 206, 82);

  }
}
</style>