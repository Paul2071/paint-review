<template>
 <div class="home">
  <h1>Home</h1>
  <input type="text" v-model="search">
  <p>{{  search  }}</p>
  <div v-for="name in matchingNames" :key="name">
      {{ name }}
  </div>
  <button @click=handleClick>stop watching</button>
</div>
  <router-view/>
</template>

<script>
import { ref, computed, watch, watchEffect } from 'vue'

export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref( ['Stormfiend ', 'Celestium Blue', 'Gutrippa Flesh ', 'Aeldari Emerald'])

    const stopWatch = watch(search, ()=> {
      console.log('watch function fired')
    })

   const stopEffect = watchEffect(( )=>{
      console.log('watcheffect', search.value)
    })


    const matchingNames = computed( ()=> {
      return names.value.filter( (name)=> name.includes(search.value))
    })

    const handleClick = () => {
      stopWatch(
      
      )
      stopEffect()
    }
    
    return { names, search, matchingNames, handleClick }
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
