<template>
  <div class="topbar">
    <h2>VueResumer</h2>
    <span></span>
    <div class="button">
      <el-button type="primary">注册</el-button>
      <el-button>登录</el-button>
    </div>

  </div>
</template>
<script>
  export default {
    name: "topbar",
    data () {
      return {
        msg: 'mine test'
      }
    }
  }
</script>

<style lang = 'scss'>
  .topbar{
    background: white;
    width: 100%;
    display:flex;
    justify-content: space-between;
    box-shadow: 0 0 3px rgba(0,0,0,.5);
    position:relative;
    z-index:1;
    height: 84px;
    align-items: center;
    padding: 16px;
    h2{
      font-size : 24px;
      font-weight: normal;
      line-height: 32px;
    }
    .button{
      button{
        padding: 8px 16px;
        text-align: center;
      }
    }
  }

</style>
