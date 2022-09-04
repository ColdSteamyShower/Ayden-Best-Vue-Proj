<template>
    <div class="card-container">
      <div class="card" :class="{flipped: isClicked}" @click="toggleClicked">
        <div class="front">
          <img class="front-icon" src="../assets/bone.svg"/>
        </div>
        <div class="back">
          <header>{{num}}</header>
          <div id="card-body">Body</div>
          <footer>Footer</footer>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  
  export default {
    name: 'CardInstance',
    data() {
      return {isClicked: false}
    },
    props: {
      dog: String,
      num: Number
    },
    methods: {
      toggleClicked: function() {
        this.isClicked = !this.isClicked;
      }
    }
  }
  </script>
  
  <style>
    .card-container {
      height: 40%;
      margin: 2%;
      padding: 2px;
      background-color: transparent;
      border-radius: 12px;
      overflow: hidden;
      flex: 0 1 15%;
      transition: transform 0.2s ease;
    }

    .card {
      position: relative;
      height: 100%;
      width: 100%;
      transform-style: preserve-3d;
      transition: all 0.6s ease;
    }

    .card-container:hover {
      transform: translateY(-10px);
    }

    .flipped {
      transform: rotateY(180deg)
    }

    .front {
      position: absolute;
      height: 100%;
      width: 100%;
      background-color: rgb(238, 238, 238);
      backface-visibility: hidden;
      display: flex;
      justify-content: center;
      border: 1px solid lightgray;
    }

    .back {
      position: absolute;
      height: 100%;
      width: 100%;
      background-color: gray;
      transform: rotateY(180deg);
      backface-visibility: hidden;
    }

    .front-icon {
      width: 60%;
      filter: opacity(10%);
      transform: rotate(45deg)
    }

    header, footer {
      background-color: lightblue;
      height: 25%;
      width: 100%;
    }

    #card-body {
      height: 50%;
    }
  </style>