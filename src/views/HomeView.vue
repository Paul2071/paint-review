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

    
    const name = ref("mario")
    const  age = ref(30)
    
    const handleClick =  () => {
      console.log(p, p.value)
      p.value.classList.add('test')
      name.value= "more test"

    }


    return {  name, age, handleClick, p }
  }
  
}
</script>
