<template>
 <div class="home">
  <h1>Home</h1>
  <input type="text" v-model="search">
  <p>{{  search  }}</p>
  <div v-for="name in matchingNames" :key="name">
      {{ name }}
  </div>
  
</div>
  <router-view/>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref( ['Stormfiend ', 'Celestium Blue', 'Gutrippa Flesh ', 'Aeldari Emerald'])

    const matchingNames = computed( ()=> {
      return names.value.filter( (name)=> name.includes(search.value))
    })
    
    return { names, search, matchingNames }
  }, 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


</style>
