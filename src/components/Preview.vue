<template>
  <div class="preview">
    <h1>面试简历 - {{resume.profile.name || '姓名'}}</h1>
    <br>
    <h2>基本信息</h2>
    <br>
    {{resume.profile.name || '请填写姓名'}}
    <br>
    {{resume.profile.birth || ''}}
    <br>
    {{resume.profile.city || ''}}
    <br>
    {{resume.contacts.qq || ''}}
    <br>
    {{resume.contacts.wechat || ''}}
    <br>
    {{resume.contacts.email || ''}}
    <br>
    <h2>工作经历</h2>
    <ol>
      <li v-for="(key,index) in resume.workHistory" v-bind:index="index">
        <div v-for ="work in works('workHistory')">
          <p>{{key[work]}}</p>
        </div>
      </li>
    </ol>
    <h2>学习经历</h2>
    <ol>
      <li v-for="(key,index) in resume.studyHistory" v-bind:index="index">
        <div v-for ="work in works('studyHistory')">
          <p>{{key[work]}}</p>
        </div>
      </li>
    </ol>
    <h2>项目经历</h2>
    <ol>
      <li v-for="(key,index) in resume.projects" v-bind:index="index">
        <div v-for ="work in works('projects')">
          <p>{{key[work]}}</p>
        </div>
      </li>
    </ol>
    <h2>获奖情况</h2>
    <ol>
      <li v-for="(key,index) in resume.awards" v-bind:index="index">
        <div v-for ="work in works('awards')">
          <p>{{key[work]}}</p>
        </div>
      </li>
    </ol>
  </div>
  <!--resume: {-->
  <!--profile: { name: '', city: '', birth: '' },-->
  <!--workHistory: [ {company: '', content: ''}, ],-->
  <!--studyHistory: [ {school: '', duration: '', degree: ''} ],-->
  <!--projects: [ {name: '', content: '' } ],-->
  <!--awards: [ {name: ''} ],-->
  <!--contacts: { qq: '', wechat: '', phone: '', email: '' }-->
  <!--}-->
</template>
<script>
  export default {
    name: "preview",
    props:['resume'],
    data () {
      return {
        msg: 'mine test'
      }
    },
    methods: {
      works(points){
        let work = this.resume[points]
        console.log(work)
        return Object.keys(work[0])
      }
    },
  }
</script>
<style lang="scss">
  .preview{
    overflow: auto;
    padding: 16px 32px;
    flex-grow: 1;
    background: white;
    border-radius: 4px;
    margin-right: 16px;
    box-shadow: 0 0 3px rgba(0,0,0,.5);
    li{display:block}
  }

</style>
