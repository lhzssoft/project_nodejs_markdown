<template>
  <ul>
    <li v-for='(e,i) in iconOptions' :key='i' >
      <button><i  v-bind:class="['iconfont', e.class]"></i></button>
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
