<template>
  <div id="app">
    <topbar></topbar>
    <div id="main">
      <editor></editor>
      <preview></preview>
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
  }
}
</script>

<style lang="scss">
  *{margin:0;
    padding:0;
    box-sizing:border-box
  };
  html, body, #app{ height: 100%; overflow: hidden; }
  #app{
    display:flex;
    flex-direction:column;
    #main{
      flex-grow: 1;
      background: #ddd;
      padding: 16px 0;
      display: flex;
    }
  }

</style>
