<template>
  <div>
    <h1>2048</h1>
    <p>Score: {{score}} Best: {{best}}</p>
    <button @click="chip = true">New Game</button>
    <br>
    <div class="table">
      <div class="box" v-for="a in newGameStart" :key="a">
        <!-- <div v-if="chip || a===rand || a==2" class="chip">{{a}}</div> -->
        <ceil v-if="chip || a===rand" :ceil="a"></ceil>  
      </div>
    </div>
  </div>
</template>

<script>
  import ceil from './ceil'
  export default {
    data() {
      return {
        score: 0,
        best: 0,
        col: 16,
        chip: false,
        number: 2,
        rand: 0,
      }
    },
    computed: {
      newGameStart() {
        this.rand = Math.floor((Math.random() * 16) + 1);
        console.log(this.rand)
        return this.col
      }
    },
    components: {
      ceil,
    },
  }
</script>

<style scoped>
  .table{
    display: flex;
    flex-wrap: wrap;
    width: 420px;
    height: 420px;
    background: #35495E;
    margin: 2% auto 5%;
    padding-bottom: 0.7027%;
    border-radius: 1.75%;
  }
  .box{
    background: #41B883;
    width: 21.6216%;
    height: 21.6216%;
    margin-left: 2.7027%;
    margin-top: 2.7027%;
    position: relative;
    border-radius: 7%;
  }
</style>