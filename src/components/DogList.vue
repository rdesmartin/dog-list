<template>
  <div>
    <div v-for="(item, key) in dogs" v-bind:key="key">
    	<div>{{dogs.join(', ')}}</div>
      <DogProfile v-bind:breed="item.breed" v-bind:name="item.name" v-bind:key="key"/>
    </div>
  </div>
</template>

<script>
import DogProfile from './DogProfile.vue'

export default {
  name: 'DogList',
  components: {
    DogProfile
  },
  props: {
    dogs: Array
  }
}
</script>
