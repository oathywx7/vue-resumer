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
              name: '石乐志',
              city: '北海以南',
              birth: '1994.2.1',
          },
          workHistory: [{
              company: '北上广公司',
              dexc: '公司总部设在XXXX区，先后在北京、上海成立分公司。专注于移动XXX领域，主打产品XXXXX，它将资讯、报纸、杂志、图片、微信等众多内容，按照用户意愿聚合到一起，实现深度个性化 定制。\n 我的主要工作如下: \n1. 完成既定产品需求。 \n2. 修复 bug。',
              time: '1998~2000',
          }],
          Education: {
              school: '蓝翔技术专修学院',
              content: '中国山东找蓝翔',
          },
          experience: [
              {
                  project: 'project A',
                  content: '巴拉巴拉',
              }
          ],
          Trophy: [{
              name: '好人卡',
              content: '你是个好人，但是我们不能在一起 ',
          }],
          contact: {
              photo: '15012345678',
              email: '159268347@sina.com',
              place: '霍尔沃兹魔法学院',
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
