<template>
  <CodeCompileView></CodeCompileView>
</template>

<script>
import CodeCompileView from '@/components/CodeCompileView'

export default {
  name: 'App',
  components: {
    CodeCompileView
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
