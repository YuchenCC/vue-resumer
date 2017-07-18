<template>
  <div id="app">
    <topbar v-if="previewSwitch === true"></topbar>
    <div id="main">
      <editor v-bind:resume="resume" v-if="previewSwitch === true"></editor>
      <preview v-bind:resume="resume" v-bind:class="{pre : previewSwitch === false,view : previewSwitch === true}"></preview>
    </div>
    <el-button class='viewButton'type="primary"  v-if="previewSwitch === true" v-on:click="previewSwitch = false">预览</el-button>
    <el-button class='viewButton' v-if="previewSwitch === false" v-on:click="previewSwitch = true">取消预览</el-button>
  </div>
</template>

<script>
 import Topbar from './components/Topbar'
 import Editor from './components/Editor'
 import Preview from './components/Preview'

export default {
  name: 'app',
  components: {
    Topbar,Editor,Preview
  },
  data() {
    return{
      previewSwitch:true,
      previewMode: false,
      resume: {
        profile: { name: '', city: '', birth: '' },
        workHistory: [ {company: '', content: ''}, ],
        studyHistory: [ {school: '', duration: '', degree: ''} ],
        projects: [ {name: '', content: '' } ],
        awards: [ {name: ''} ],
        contacts: { qq: '', wechat: '', phone: '', email: '' }
      }
    }
  }
}
</script>

<style lang="scss">

  *{
    font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    margin:0;
    padding:0;
    box-sizing:border-box;
    ol,ul{
      list-style: none;
      li{
        list-style: none;
      }
    }
    a{
      color: inherit;
      text-decoration: none;
    }
  };

  html, body, #app{ height: 100%; overflow: hidden; }
  #app{
    display:flex;
    flex-direction:column;
    #main{
      height: 100%;
      background: #ddd;
      padding: 16px 0;
      display: flex;
    }
    @media (max-width: 750px){
      #main{
        flex-direction:column;
      }
      .view{
        display:none;
      }
    }
  }
  .viewButton{
    position: absolute;
    bottom: 24px;
    right: 40px;
  }
  .pre{
    width: 60%;
    padding: 64px;
    margin: 0 auto;
    box-shadow: 0 0 3px rgba(0,0,0,.5);
    background: #F9FAFC;
    border-radius: 4px;
    overflow: auto;
    min-width: 600px;
  }

  .view{
    overflow: auto;
    padding: 32px 32px;
    flex-grow: 1;
    background: white;
    border-radius: 4px;
    margin-right: 16px;
    box-shadow: 0 0 3px rgba(0,0,0,.5);
  }
  @media (max-width: 750px){
    .pre {
      width: 96%;
      border-radius: 0;
      margin: 8px auto;
      margin-bottom:0;
    }
    .view{
      margin-right: 16px;
    }
  }
</style>
