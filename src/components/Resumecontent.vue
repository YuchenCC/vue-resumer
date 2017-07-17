<template>
  <div>
    <h2>2313</h2>
  </div>




</template>
<style lang="scss">
  h2{
    width:100px;
    height:100px;
  }
</style>

<script>
  import Editor from './Editor.vue'
  export default {
    props: ['resume'],
    components: {Editor},
    name: "resumecontent",
    data() {
      return {
        labelPosition: 'top',
        content: [
        	{
            title: '个人信息',
            nameLabel: '姓名',
            name: '',
            cityLabel:'城市',
            city: '',
            birthLabel:'出生年月',
            birth: ''
          },
          {
            title: '工作经历',
            work: [{
              companyLabel: '公司',
              company: '',
              workDetialLabel:'工作内容',
              workDetial: ''
            }]
          },
          {
            title: '学习经历',
            work: [{
              schoolLabel: '学校',
              school: '',
              durationLabel:'时间',
              duration: '',
              degreeLabel: '',
              degree: ''
            }]
          }
       ]
      };
    }
  }
</script>
