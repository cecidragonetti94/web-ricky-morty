<template>
  <div class="search">
    <input
      type="text"
      placeholder="Search by name"
      v-model="name"
      @keyup="filter()"
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
</style>