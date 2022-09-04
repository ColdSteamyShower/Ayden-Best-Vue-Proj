<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div id="card-container">
      <cardInstance  v-for="(dog, index) in dogs.message" :key="index" :dog="dog" :num="index+1"/>
  </div>
</template>

<script>
import CardInstance from './components/CardInstance.vue'

export default {
  name: 'App',
  components: {
    CardInstance
  },
  data() {
    return {
      dogs: {}
    }
  },
  async created() {
    fetch("https://dog.ceo/api/breeds/image/random/10")
    .then(response => response.json())
    .then(data => (this.dogs = data));
  }
}
</script>

<style>
* {
  margin: 0px;
  padding: 0px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#card-container {
  border: 1px dashed red;
  margin: 0px 10% 0px 10%;
  height: 70vh;
  width: 80%;
  bottom: 5%;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between
}
</style>
