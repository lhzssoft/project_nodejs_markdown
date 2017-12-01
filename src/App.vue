<template>
  <div id='app'>
    <c-toolbar ref='toolbar' :style='{height:height}'></c-toolbar>
    <c-container height='cHeight'></c-container>
  </div>
</template>

<script>
  import Toolbar from './components/Toolbar'
  import Container from './components/Container'

  export default {
    name: 'app',
    components: { 'c-toolbar' : Toolbar , 'c-container' : Container } ,
    props:[
      'height'
    ],
    data(){
      return {
        cHeight : ''
      } ;
    } ,
    mounted(){
      let foo = this.$refs.toolbar.offsetHeight ;
      this.cHeight = `calc(100% - ${foo}px)` ;
    }
  }
</script>

<style lang='stylus' scoped>
  #app
  //   height : 100%
  //   margin : 0
    box-sizing: border-box

</style>
