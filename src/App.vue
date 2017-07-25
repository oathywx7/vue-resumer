<template>
  <div id="app" v-bind:class="{previewMode:previewMode}">
    <Topbar class="topbar" v-on:preview="preview"/>
    <main>
      <Editor v-bind:resume="resume" class="editor"/>
      <Preview v-bind:resume="resume" class="preview"/>
    </main>
    <el-button id="exitPreview" v-on:click="exitPreview">退出预览</el-button>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Editor from './components/Editor'
import Preview from './components/Preview'

export default {
    data(){
      return{
        previewMode: false,
        resume: {
          labelPosition: '',
          Profile: {
              name: '',
              city: '',
              birth: '',
          },
          workHistory: [{
              company: '',
              dexc: '',
              time: '',
          }],
          Education: {
              school: '',
              content: '',
          },
          experience: [
              {
                  project: '',
                  content: '',
              }
          ],
          Trophy: [{
              name: '',
              content: '',
          }],
          contact: {
              photo: '',
              email: '',
              place: '',
          }
        }
      }
    },
    methods:{
      exitPreview(){
        this.previewMode = false
      },
      preview(){
        this.previewMode = true
      }
    },

    components:{
      Topbar,Editor,Preview
    },
}
</script>

<style >
html, body, #app{
  height: 100%;
  overflow: hidden;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*height: 100vh;*/
  display: flex;
  flex-direction: column;
}

.topbar{
  position: relative;
  z-index: 1;
  box-shadow: 0 0 1px ;
}
.icon {
       width: 1em; height: 1em;
       vertical-align: -0.15em;
       fill: currentColor;
       overflow: hidden;
       
}

main{
  display: flex;
  flex: 1;
  background: #ddd;
}
main > .editor{
  width: 40em;
  margin: 16px 8px;
  background: #fff;
  box-shadow: 0 0 1px ;
  border-radius: 4px;
  overflow: hidden;
}
main > .preview{
  flex: 1;
  margin: 16px 8px;
  background: #fff;
  box-shadow: 0 0 1px ;
  border-radius: 4px;
  overflow: hidden;
}
.previewMode > #topbar{
  display: none;
}
.previewMode #editor{
  display: none;
}
.previewMode #preview{
  max-width: 800px;
  margin: 16px auto;
}
#exitPreview{
  display: none;
}
.previewMode #exitPreview{
  display: inline-block;
  position: fixed;
  right: 16px;
  top: 16px;
}

</style>
