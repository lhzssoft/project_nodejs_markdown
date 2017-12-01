<template>
  <div id='app'>
    <c-toolbar></c-toolbar>
    <c-container></c-container>
  </div>
</template>

<script>
  import Toolbar from './components/Toolbar'
  import Container from './components/Container'

  export default {
    name: 'app',
    components: { 'c-toolbar' : Toolbar , 'c-container' : Container }
  }
</script>

<style lang='stylus'>
  html, body, #app
    height : 100%
    margin : 0
    box-sizing: border-box
</style>
