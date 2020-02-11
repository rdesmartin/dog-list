<template>
    <div>
        <h1>{{name + ' (' + breed + ')'}}</h1>
        <img v-bind:src="imgUrl" />
    </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'DogProfile',
  props: {
    breed: String,
    name: String
  },
  data () {
    return {
      imgUrl: "",
    }
  },
  methods: {
    fetchData: async function() {
      const res = await axios.get("https://dog.ceo/api/breed/" + this.breed + "/images/random")
      // eslint-disable-next-line
      console.log(res);
      this.imgUrl = res.data.message;
    }
  },
  mounted() {
    this.fetchData()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
