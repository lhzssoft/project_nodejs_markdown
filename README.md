# foo-markdown

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## How to Use

+ npm install --save github:lhzssoft/project_nodejs_markdown

+ scripts

  ```
  import Markdown from 'foo-markdown/src/App.vue'

  export default {
    name: 'app',
    components: {'c-markdown': Markdown },
    data(){
      return {
        cHeight:'100%'
      } ;
    },
    mounted () {
      let foo = this.$refs.img.scrollHeight  ;
      this.cHeight = `calc(100% - ${foo}px - 1px - 20px)` ;
    }
  }
  ```
 + templates

   ```
   <c-markdown :height='cHeight'></c-markdown>
   ```
