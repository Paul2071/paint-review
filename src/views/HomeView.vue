<template>
  <div class="home">
    <h1>homepage</h1>

    <p ref="p"> my name is {{ name }} and i am {{ age }}</p>
    <button @click="handleClick">click me</button>
  </div>
</template>

<script>

import {ref} from "vue"

export default {
  name: 'HomeView',
  setup() {

    const p = ref(null)

    
    let name = "mario"
    let age = 30
    
    const handleClick =  () => {
      console.log(p)
    }


    return {  name, age, handleClick, p }
  }
  
}
</script>
