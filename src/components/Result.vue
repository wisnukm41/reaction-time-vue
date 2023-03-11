<template>
  <p>Your reaction time is {{score}} ms</p>
  <div class="result">{{rank}}</div>
</template>

<script>
export default {
    props : ['score'],
    data(){
        return {
            rank : null
        }
    },
    mounted(){
        if(this.score < 300) {
            this.rank = "You are a GODSPEED Human BEING"
        } else if(this.score < 500) {
            this.rank = "You are a fast Human BEING"
        } else {
            this.rank = "You are a DISGRACE"
        }
    }
}
</script>

<style>
    .result{
        font-size: 1.2rem;
        color: #38E54D;
        font-weight: bold;
    }
</style>