<template>
  <div class="preview">

  </div>
</template>
<script>
  export default {
    name: "preview",
    data () {
      return {
        msg: 'mine test'
      }
    }
  }
</script>
<style lang="scss">
  .preview{
    flex-grow: 1;
    background: white;
    border-radius: 4px;
    margin-right: 16px;
    box-shadow: 0 0 3px rgba(0,0,0,.5)
  }
</style>
