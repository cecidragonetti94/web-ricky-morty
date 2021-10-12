<template>
  <div class="filter">
    <div class="item" @click="filter('')">
      All
    </div>
    <div class="item" @click="filter('Alive')">
      Alive
    </div>
    <div class="item" @click="filter('Dead')">
      Dead
    </div>
    <div class="item" @click="filter('unknown')">
      Unknown
    </div>
  </div>
</template>

<script>
import { useStore } from 'vuex'
export default {
  setup() {
    const store = useStore()
    const filter = ((status) => {
      store.dispatch('filterByStatus', status)
    })
    return {
      filter
    }
  }
}
</script>

<style>
.filter{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-weight: bolder;
  margin-bottom: 10px;
  cursor: pointer;
 
}
.item:hover{
  color:rgb(48, 206, 82);
}
@media screen and (min-width: 485px){
 .filter{
   font-size: 25px;
 } 
 .item:hover{
  color:rgb(48, 206, 82);
}
}
</style>