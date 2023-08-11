<template>
 <div class="home">
  <h1>Home</h1>
  <p> {{ name }}</p>  
</div>
  <router-view/>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  name: 'Home',
  setup() {
    const name = computed( ()=> {
      return 'paul'
    }

    )
    return { name }
  }
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
