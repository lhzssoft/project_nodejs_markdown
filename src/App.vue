<template>
  <div id='app'  :style='{height:height}'>
    <c-toolbar></c-toolbar>
    <c-container class='c-height'></c-container>
  </div>
</template>

<script>
  import Toolbar from './components/Toolbar'
  import Container from './components/Container'

  export default {
    name: 'app',
    components: { 'c-toolbar' : Toolbar , 'c-container' : Container } ,
    props: [
      'height'
    ],
    data(){
      return {
      } ;
    } ,
    beforeCreate(){

    }
  }
</script>

<style scoped>
  #app {
      box-sizing: border-box
  }

  .c-height {
    height : calc(100% - 38px - 1px) ;
  }

</style>
