<template>
  <div>
    <h2>个人信息</h2>
    <el-form class="resumeInfo">
      <el-form-item label="姓名">
        <el-input v-model="profile.name"></el-input>
      </el-form-item>
      <el-form-item label="城市">
        <el-input v-model="profile.city"></el-input>
      </el-form-item>
      <el-form-item label="出生年月">
        <el-input v-model="profile.birth"></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
  export default {
  	name: 'ProfileEditor',
    props: ['profile']
  }
</script>
<style lang="scss">
  .resumeInfo{
    margin-top: 20px;
  }
</style>
