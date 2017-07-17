<template>
  <div class="editor">
    <nav>
      <ol>
        <li v-for="(icon,index) in icons" v-on:click="currentTab = index" v-bind:class="{active: currentTab === index}">
          <svg class="icon">
            <use v-bind:xlink:href="`${icon}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <div class="content">
      <ol>
        <li v-for="(icon,index) in icons" v-if="currentTab === index">
          <h3>{{icon}}</h3>
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
  export default {
    name: "editor",
    data () {
      return {
        currentTab: 0,
        icons:['#icon-shenfenzhengzhengjian','#icon-work','#icon-Learningmanagement','#icon-huojiangzuopin','#icon-jinlingyingcaiwangtubiao67','#icon-iconfontphone17']
      }
    }
  }
</script>
<style lang="scss">
  .editor{
    background: white;
    border-radius: 4px;
    width: 30%;
    margin: 0 16px;
    box-shadow: 0 0 3px rgba(0,0,0,.5);
    display: flex;
    overflow:hidden;
    > nav{
      background: black;
      height:100%;
      width: 30%;
      max-width: 80px;
      li{
        background: black;
        min-height: 32px;
        padding: 16px 0;
        .icon{
          display:block;
          margin: 0 auto;
          fill: white;
          width: 26px;
          height: 26px;
          line-height: 32px;
        }
      }
      .active{
        .icon{
          fill: black;
        }
        background: white;
      }


    }
    > .content{
      flex-grow:1;

    }
  }
</style>
