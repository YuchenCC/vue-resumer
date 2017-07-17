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
        <li v-if="currentTab === 0">
          <ProfileEditor v-bind:profile="resume.profile"></ProfileEditor>
        </li>
        <li v-if="currentTab === 1">
          <ArrayEditor title="工作经历" v-bind:items="resume.workHistory" v-bind:labels="['公司','工作内容']"></ArrayEditor>
        </li>
        <li v-if="currentTab === 2">
          <ArrayEditor title="学习经历" v-bind:items="resume.studyHistory" v-bind:labels="['学校','时间','学位']"></ArrayEditor>
        </li>
        <li v-if="currentTab === 3">
          <ArrayEditor title="项目经历" v-bind:items="resume.projects" v-bind:labels="['项目名称','工作内容']"></ArrayEditor>
        </li>
        <li v-if="currentTab === 4">
          <ArrayEditor title="获奖情况" v-bind:items="resume.awards" v-bind:labels="['奖励详情']"></ArrayEditor>
        </li>
        <li v-if="currentTab === 5">
          <h2>联系方式</h2>
          <el-form>
            <el-form-item label="QQ">
              <el-input v-model="resume.contacts.qq"></el-input>
            </el-form-item>
            <el-form-item label="微信">
              <el-input v-model="resume.contacts.wechat"></el-input>
            </el-form-item>
            <el-form-item label="邮箱">
              <el-input v-model="resume.contacts.email"></el-input>
            </el-form-item>
            <el-form-item label="手机">
              <el-input v-model="resume.contacts.phone"></el-input>
            </el-form-item>
          </el-form>
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
  import ProfileEditor from './ProfileEditor'
  import ArrayEditor from './ArrayEditor'
  export default {
    components:{ ProfileEditor, ArrayEditor},
    name: "editor",
    props: ['resume'],
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
      ol{
        li{
            background: white;
            width: 70%;
            margin: 0 auto;
            margin-top: 48px;

        }
      }

    }
  }
</style>
