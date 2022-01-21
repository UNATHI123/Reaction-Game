<template>
  <img src="https://images.pexels.com/photos/5942185/pexels-photo-5942185.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260" alt="Vue" >
    <h1>Young Grasshoper Reaction Time</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" @done="endGame"/>
  <Results v-if="showResults" :score="score"/>
  </template>

<script>
  import Block from './components/Block.vue';
  import Results from './components/Results.vue';
export default {
  name: 'App',
  components: {
  Block,
  Results

  },
  data(){
    return{
      isPlaying:false,
      delay:null,
      score:null,
      showResults:false
    }
  },
  methods:{
    start(){
      this.delay =2000 +Math.random() *5000;
      this.isPlaying = true; 
      this.showResults =false;
        },

        endGame(reactionTime){
          this.score = reactionTime;
          this.isPlaying = false;
          this.showResults = true;
        }
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button{
  background: crimson;
  color:white;
  border:none;
  padding: 8px 16px;
  border-radius:4px ;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}

button[disabled]{
  opacity: 0.2;
  cursor:not-allowed;
}
img{
  width: 300px;
  height: 300px;
}
</style>
