<template>
  <div class="app-title">
    <img src="./assets/profile-pic.jpg"/>
    <div class="title-content">
      <header>Purpose Financial Coding Challenge</header>
      <p>Solution provided by Ayden Best</p>
      <a href="https://www.linkedin.com/in/ayden-best-9a506520b/">View my profile on LinkedIn!</a>
    </div>
  </div>
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
  font-family: Consolas, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#card-container {
  margin: 0px 10% 0px 10%;
  height: 70vh;
  width: 80%;
  bottom: 5%;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between
}

.app-title {
  height: 15vh;
  width: 60%;
  min-width: 600px;
  margin: auto;
  margin-top: 20px;
  display: flex;
  align-items: center;
  background: rgb(120,170,255);
  background: linear-gradient(90deg, rgba(120,170,255,1) 0%, rgba(120,170,255,1) 80%, rgba(0,0,0,0) 100%);
  border-radius: 80px 0px 0px 80px
}

.app-title img {
  height: 70%;
  margin-left: 3%;
  margin-right: 50px;
  border-radius: 50%
}

.title-content {
  display: flex;
  flex-direction: column;
  align-items: start;
}

.title-content > header {
  font-weight: 600;
  font-size: 20px;

}

.title-content > * {
  background: transparent;
  margin-bottom: 5px;
  color: white
}
</style>
