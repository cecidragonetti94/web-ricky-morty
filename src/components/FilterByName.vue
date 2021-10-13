<template>
  <div class="search">
    <input
      type="text"
      placeholder="Search by name"
      v-model="name"
      @keyup="filter()"
      class="input-name"
    >
  </div>
</template>

<script>
import { ref } from 'vue'
import { useStore } from 'vuex'
export default {
  setup() {
    const name = ref('')
    const store = useStore()
    const filter = () => {
      store.dispatch('filterByName', name.value)
    }
    return {
      name,
      filter
    }
  }
}
</script>


<style>
.input-name{
  border: 2px solid rgb(48, 206, 82);
  border-radius: 5px;
  height: 40px;
  margin: 5px 7px;
}
.input-name:hover{
  background-color: #ccc;
}

</style>