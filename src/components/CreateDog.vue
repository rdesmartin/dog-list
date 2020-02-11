<template>
  <div>
    <input type="text" v-model:value="name" placeholder="Name" />
    <input type="text" v-model:value="breed" placeholder="Bred"/>
    <button v-on:click="addDog({name, breed})">Add Dog</button>
  </div>
</template>

<script>
  export default {
    name:'CreateDog',
    data() {
      return {
        name: "",
        breed: ""
      }
    },
    props: {
      addDog: Function
    }
  }
</script>
