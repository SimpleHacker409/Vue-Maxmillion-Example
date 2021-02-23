<template>
  <button v-on:click="csv2json">conver csv to json</button>
<p v-for:="cat in output">{{cat.name}}</p>
<p>{{ output }}</p>


<select name="cats" id="cats">
  <option v-for:="cat in output" value="c">{{ cat.name }}</option>
</select>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
 let csvToJson = require ('convert-csv-to-json');


// import csvtojson from 'csvtojson'
// import fs from 'fs'
// const csvfilepath = 'careplans.csv'


export default {

  name: 'App',
  components: {
    // HelloWorld
    // csvToJson,
 
  },
  data(){
    
    return{
message: 'Hi',
fileInputName : 'careplans.csv',
output:[
{"name": "cat1", "age":"22"},
{"name": "cat2", "age":"22"},
{"name": "cat3", "age":"22"}
],

};
  },
  methods:{
  csv2json(){
     
  this.output = csvToJson.getJsonFromScv(this.fileInputName);
  for (let i = 0; i < this.output.length; i++) {
    this.output.push(this.output[i])
    
  }

   
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
