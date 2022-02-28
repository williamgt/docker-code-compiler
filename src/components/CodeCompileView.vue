<template>
  <div class="compiler-container">
    <h1>Please enter your code:</h1>
    <textarea v-model="codeRepresentation.code" id="code-input"></textarea>
    <button id="compile-button" @click="compile">Compile</button>
    <h1>Output:</h1>
    <p id="output">{{output}}</p>
    <p>{{ this.code }}</p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'CodeCompileView',
  data () {
    return {
      codeRepresentation: {
        code: ''
      },
      output: ''
    }
  },
  methods: {
    compile () {
      axios.post('http://localhost:8085/execute', this.codeRepresentation)
        .then(response => {
          this.output = response.data
        })
    },
    dummyCompile () {
      axios.get('http://localhost:8085/test/' + this.codeRepresentation.code)
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
