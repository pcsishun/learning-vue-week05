<template>
  <div id="app">
    <p>{{ score }}</p>
    <p v-show="score > 10">passing</p>
    <p v-show="score <= 10" @clicl="remover">Failing</p>

    <button  @click="add">add</button>
    <button  @click="remover">remove</button>
    <p v-if="score > 10">More than 10</p>
    <p v-else >less than 10</p>
    <hr>
    <input  type="number" v-model="score2" />
    <button @click="gradeCal">cal</button>
    <p v-if="score2 > 50 && score2 <=60">D 2</p>
    <p v-if="score2 > 60 && score2 <=70">C 2</p>
    <p  v-if="score2 > 70 && score2 <=80">B 2</p>
    <p  v-if="score2 > 80">A 2</p>
    <p>{{ garde }}</p>
  </div>
</template>

<script>
 

export default {
  name: 'App',
  data(){
    return{
      score: 0,
      score2:0,
      garde: null
    }
  },
  methods:{
    add(){
      this.score += 5;
    },
    remover(){
      this.score -= 5;
    },
    gradeCal(){
      if(this.score2 >= 50){
        this.garde = 'D'
      }
      if(this.score2 >= 60){
        this.garde = 'C'
      }
      if(this.score2 >= 70){
        this.garde = 'B'
      }
      if(this.score2 >= 80){
        this.garde = 'A'
      }
      if(this.score2 > 100){
        this.garde = "Worng Score"
      }
 
    }
  }
 
}
</script>

<style>

</style>
