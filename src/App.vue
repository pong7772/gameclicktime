<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue'
export default{
  name: 'App',
  components: {Block, Results},
  data(){
    return{
      isPlaying: false,
      delay: null,
      score:null,
      showResult: false
    }
  },
  methods:{
    handlePlay(){
      this.isPlaying = true ;
      this.delay = 2000 + Math.random() *3000;
      this.showResult =false
    },
    endGame(reactionTime){
      this.score= reactionTime;
      this.isPlaying = false;
      this.showResult = true;
    }
  }
}
</script>

<template>
<div class="wrapper">
<h1 >Pong Reaction Timer</h1>
<button @click="handlePlay" :disabled="isPlaying">Play Game</button>
<Block v-if="isPlaying == true" :delay="delay" @end="endGame"/>
<Results v-if="showResult" :score="score"/>
</div>
</template>

<style scoped>
.wrapper{
  text-align: center;
}
</style>