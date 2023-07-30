<template>
  <div class="home">
    <h1>homepage</h1>

    <p> my name is {{ name }} and i am {{ age }}</p>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  setup() {
    let name = "mario"
    let age = 30

    return {  name, age}
  }
  
}
</script>
