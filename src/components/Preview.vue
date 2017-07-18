<template>
  <div class="preview">
    <h1>面试简历 - {{resume.profile.name || '姓名'}}</h1>
    <br>
    <h2>基本信息</h2>
    <br>
    <p>{{resume.profile.name || '姓名'}}</p>
    <br>
    <p>{{resume.profile.birth || '填写出生日期' }}</p>
    <br>
    <p>{{resume.profile.city || '所在城市'}}</p>
    <br>
    <p>{{resume.contacts.qq || 'QQ'}}</p>
    <br>
    <p>{{resume.contacts.wechat || '微信'}}</p>
    <br>
    <p>{{resume.contacts.email || 'Email'}}</p>
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
          <p >{{key[work]}}</p>
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
        record: 0
      }
    },
    methods: {
      works(points){
        let work = this.resume[points]
        //console.log(work)
        return Object.keys(work[0])
      }
    },
    create: {
    	fn(){console.log('create')}

    }
  }
</script>
<style lang="scss">
  .preview{

    li{display:block}
    *{
      line-height: 1.5em;
    }
  }

</style>
