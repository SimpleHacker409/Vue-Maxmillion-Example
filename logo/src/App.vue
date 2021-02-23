<template>
  <img alt="Vue logo" src="./assets/logo.png" v-bind:width="size" v-bind:height="size" >
  <button v-on:click="logosmall"> small </button>
  <button v-on:click="logomedium"> Medium </button>
  <button v-on:click="logolarge"> Large </button>
  <input type="text" v-model="size"/>
  

</template>

<script>


export default {
  name: 'App',
  components: {
    
    },
    data(){
      return{
        width:"300",
        height:"300",
        size:"300"

      };
    },
    methods:{
      logosmall(){
        this.width = "100"
        this.height="100"

      },
      logomedium(){
        this.width="200"
        this.height="200"
      },
      logolarge(){
        this.width="400"
        this.height="400"
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
</style>
