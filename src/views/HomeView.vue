<template>
  <div class="home">
    <h1>homepage</h1>

    <p ref="p"> my name is {{ name }} and i am {{ age }}</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add to age</button>
    <input type="text" v-model="name">

    <p>{{ reftest.name }} - {{ reftest.age }}</p>
    
    <button @click="updateRefTest">updateRefTest</button>

    <p>{{ reactiveTest.name }} - {{ reactiveTest.age }}</p>

    <button @click="updateReactiveTest">updateRefTest</button>
  </div>
</template>

<script>

import {ref, reactive} from "vue"

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

    const reftest = ref({name: "paul", age: "36"})
    const reactiveTest = reactive({ name: "heather", age: 28})

    const updateRefTest = () => {
      reftest.value.age = 40
    }
    const updateReactiveTest = () => {
      reactiveTest.age = 40
    }

    

    return {  name, age, handleClick, p, reftest, updateRefTest, reactiveTest, updateReactiveTest }
  }
  
}
</script>
