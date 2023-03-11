<template>
  <div class="block" @click="endGame">
    <p>Click Me</p>
  </div>
</template>

<script>
export default {
    data(){
        return {
            startTime : null,
            reactionTime : null,
        }
    },
    mounted(){
        this.startTime = new Date()
    },
    methods:{
        endGame(){
            this.reactionTime = new Date() - this.startTime 
            this.$emit('end', this.reactionTime)
        }
    }
}
</script>

<style>
    .block{
        width: 400px;
        height: 300px;
        background-color: #38E54D;
        color: #fff;
        margin: 20px auto;
        border-radius: 10px;
        font-size: 1.2rem;
        display: grid;
        place-items: center;
    }
</style>