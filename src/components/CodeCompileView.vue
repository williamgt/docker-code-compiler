<template>
  <div class="compiler-container">
    <h1>Please enter your code:</h1>
    <textarea v-model="code" id="code-input"></textarea>
    <button id="compile-button" @click="dummyCompile">Compile</button>
    <h1>Output:</h1>
    <p id="output">placeholder {{output}}</p>
    <p>{{ this.code }}</p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'CodeCompileView',
  data () {
    return {
      code: '',
      output: ''
    }
  },
  methods: {
    compile () {
      console.log('Compiling')
      // write code to file
      // run container and pipe output to output-file
      // take contents of output file and put in output
      return 0
    },
    dummyCompile () {
      axios.get('http://localhost:8085/test/' + this.code)
        .then(response => {
          this.output = response.data
        })
    }
  }

}
</script>

<style scoped>
 .compiler-container{
   display: flex;
   flex-direction: column;
   gap: 10px;
 }
 #compile-button{
   width: 70px;
   align-self: center;
 }
 #code-input{
   width: 400px;
   height: 200px;
   align-self: center;
 }
 #output{
   width: 400px;
   height: 200px;
   align-self: center;
   border-style: solid;
   text-align: start;
 }
</style>
