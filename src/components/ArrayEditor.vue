<template>
  <div>
    <h2>{{title}}</h2>
    <el-form class="resumeInfo">
      <div v-for="(item,index) in items" v-bind:index="index">
        <el-form-item v-for="(key,index) in keys" v-bind:label="labels[index] || key" v-bind:key="key">
          <el-input v-model="item[key]"></el-input>
        </el-form-item>
        <div class="addIcons">
          <i class="el-icon-plus" v-on:click="addWorkHistory()"></i>
          <i class="el-icon-minus" v-on:click="removeWorkHistory(index)"></i>
        </div>
      </div>
    </el-form>
  </div>
</template>


<script>
  export default {
    props: ['items','labels', 'title'],
    computed: {
      keys(){
        return Object.keys(this.items[0])
      }
    },
    methods: {
      addWorkHistory(){
      	console.log(this.items)
        const empty = {}
        this.keys.map((key)=>{
          empty[key] = ''
        })
        this.items.push(empty)
      },
      removeWorkHistory(index){
        this.items.splice(index, 1)
      }
    }
  }
</script>
<style lang="scss">
  .resumeInfo{
    margin-top: 20px;
    position: relative;
  }
  .addIcons{
    position: absolute;
    top:0;
    right: 0;
    transform: translateX(100%);
    i{
      border:1px solid #ddd;
      color :#ddd;
      padding: 3px;
      box-sizing: content-box;
    }
  }

</style>
