<template>
  <ul>
    <li v-for='(e,i) in iconOptions' :key='i' :data-class='e.class' @click='onClick'>
      <button v-bind:class="['iconfont', e.class]"></button>
    </li>
  </ul>
</template>

<script>
  export default {
    name : 'Toolbar' ,
    data() {
      return {
        iconOptions : [
          { index : 1 , class: 'icon-header' } ,
          { index : 2 , class: 'icon-bold' } ,
          { index : 3 , class: 'icon-italic' } ,
          { index : 5 , class: 'icon-underline' } ,
          { index : 6 , class: 'icon-quotes' } ,
          { index : 7 , class: 'icon-code' } ,
          { index : 8 , class: 'icon-list' } ,
          { index : 9 , class: 'icon-table' } ,
          { index : 10 , class: 'icon-link' } ,
          { index : 11 , class: 'icon-image' } ,
          { index : 12 , class: 'icon-save' } ,
          { index : 13 , class: 'icon-help' }
        ] ,
      } ;
    } ,
    methods : {
      onClick(event) {
        let foo = event.target.className ; // 'iconfont icon-header'

        if( 0 <= foo.indexOf('icon-header'))
          this.$emit('toolbarClick','\n# ') ;

        if( 0 <= foo.indexOf('icon-bold'))
          this.$emit('toolbarClick','****', -2) ;

        if( 0 <= foo.indexOf('icon-italic'))
          this.$emit('toolbarClick','**', -1) ;

        if(  0 <= foo.indexOf('icon-underline'))
          this.$emit('toolbarClick','~~~~', -2) ;

        if(  0 <= foo.indexOf('icon-quotes'))
          this.$emit('toolbarClick','> ') ;

        if(  0 <= foo.indexOf('icon-code'))
          this.$emit('toolbarClick','```\n\n```', -3-1) ;

        if(  0 <= foo.indexOf('icon-list'))
          this.$emit('toolbarClick','+ ') ;

        if(  0 <= foo.indexOf('icon-table'))
          this.$emit('toolbarClick','| Tables        | Are           | Cool  |\n'
                                   +'| ------------- |:-------------:| -----:|\n'
                                   +'| col 1 is      | centered      |   $11 |\n'
                                   +'| col 2 is      | centered      |   $12 |'
          ) ;

        if( 0 <= foo.indexOf('icon-link'))
          this.$emit('toolbarClick', '[]()' , 0-']()'.length);

        if( 0 <= foo.indexOf('icon-image'))
          this.$emit('toolbarClick', '![]()', 0-']()'.length);

        if( 0 <= foo.indexOf('icon-save'))
          this.$emit('save');
      }
    }
  }
</script>

<style lang='sass' scoped>
  @import '../assets/font/iconfont.css'

  ul
    list-style: none
    display: flex
    margin: 0
    padding: 0
    background-color: #F6F6F6
    li
      button
        height: 36px
        width: 36px
        border: none
        background: none
        outline: none
        transition: all ease .3s
        &:hover
          background: #F7F7F7
          cursor: pointer
          .iconfont
            font-color: red

</style>
