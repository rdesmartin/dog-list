<template>
  <div id="app">
    <CreateDog v-bind:addDog="addDog"></CreateDog>
    <DogList v-bind:dogs="dogs"></DogList>
  </div>
</template>

<script>
import DogList from './components/DogList.vue'
import CreateDog from './components/CreateDog.vue'

export default {
  name: 'app',
  components: {
    DogList,
    CreateDog
  },
  data() {
    return {
      dogs: []
    }
  },
  methods: {
    addDog(dog) {
      this.dogs.push(dog)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
