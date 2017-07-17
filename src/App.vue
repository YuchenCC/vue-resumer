<template>
  <div id="app">
    <topbar></topbar>
    <div id="main">
      <editor v-bind:resume="resume"></editor>
      <preview v-bind:resume="resume"></preview>
    </div>
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
  }

</style>
