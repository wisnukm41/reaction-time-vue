<template>
  <h1>Are you as Fast as you Think?</h1>
  <button @click="startTest" :disabled="isTested">Test Me</button>
  <Block v-if="isShow" @end="endGame"/>
  <Result v-if="isResult" :score="result"/>
</template>

<script>
import Block from './components/Block.vue';
import Result from './components/Result.vue';


export default {
  name: 'App',
  components: {Block, Result},
  data(){
    return {
      isTested : false,
      isShow : false,
      isResult : false,
      delay : null,
      result : null,
    }
  },
  methods : {
    startTest(){
      this.delay = 2000 + Math.random() * 5000
      this.isTested = true;
      this.isResult = false;
      
      setTimeout(()=>{
        this.isShow = true;
      },this.delay)
    },
    endGame(reactionTime){
      this.result = reactionTime;
      this.isTested = false;
      this.isShow = false;
      this.isResult = true;
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
  color: #444;
  margin-top: 60px;
}

button {
  background: lightseagreen;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 6px;
  font-size: 1.2rem;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}

button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
