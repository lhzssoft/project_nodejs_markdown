<template>
  <div id='app'  :style='{height:height}'>
    <c-toolbar @toolbarClick='toolbarClick' @save='save'></c-toolbar>
    <c-container class='c-height' ref='ref_container'></c-container>
  </div>
</template>

<script>
  import Toolbar from './components/Toolbar.vue'
  import Container from './components/Container.vue'
  import Setify from 'set-input-value'

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
    methods :{
      toolbarClick(v,shift) {

        let dom = document.getElementsByClassName('auto-textarea-input no-border no-resize')[0] ;
        Setify( dom , this.$refs.ref_container.text + v, shift ? v.length+shift : v.length );
        dom.focus() ;
      } ,
      save(){
        this.$emit('save', this.$refs.ref_container.text) ;
      }
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
