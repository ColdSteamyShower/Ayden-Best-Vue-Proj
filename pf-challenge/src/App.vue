<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div id="card-container">
    <CardInstance/>
    <CardInstance/>
    <CardInstance/>
    <CardInstance/>
    <CardInstance/>

    <CardInstance/>
    <CardInstance/>
    <CardInstance/>
    <CardInstance/>
    <CardInstance/>
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
      dogs: fetch("https://dog.ceo/api/breeds/image/random/10")
    }
  },
  watch: {
    dogs: function(newData) {
      console.log("New data for dogs: ", newData)
    }
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
  position: absolute;
  bottom: 5%;
  left: 0px;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between
}
</style>
