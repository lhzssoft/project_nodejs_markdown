<template>
  <div class='c-container'>
      <c-textarea class='c-left' autofocus fontSize='16px' lineHeight='1.5' :value='value' :onchange='change'></c-textarea>
      <div class='c-right markdown-body' v-html='html'></div>
  </div>
</template>

<script>
  import { autoTextarea } from 'auto-textarea'

  import marked from 'marked'
  import highlightjs from 'highlight.js'
  import 'github-markdown-css/github-markdown.css'
  import 'highlight.js/styles/googlecode.css'

  export default {
    name: 'Container',
    components : { 'c-textarea' : autoTextarea.default } ,
    data () {
      return {
        value: '' ,
        text:'',
        html: '',
      } ;
    } ,
    computed: {
    },
    methods : {
      change(v) {
        this.html = marked(  v, { sanitize: true,highlight: (code) => highlightjs.highlightAuto(code).value  });
        this.text = v ;
      }
    },
    mounted(){
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='sass'  scoped>

  .c-container
    display : flex
    box-sizing : border-box
    margin : 0 20px 20px 20px
    .c-right
      width: 50%
      height : 100%
      box-sizing : border-box
      border-left-style: solid
      border-left-width: 6px
      border-left-color: #F6F6F6
      padding-left: 20px
      padding-top : 10px
      padding-bottom : 10px
    .c-left
      width : 50%
      height : 100%
      box-sizing : border-box
      margin-top : 10px
      // padding-right : 10px
      >>> /deep/ textarea
        // background-color: #F6F6F6
        // padding : 20px 0px 20px 20px

</style>
