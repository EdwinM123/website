<template>
  <div class="container">
    <button type="button" class="btn btn-success">Success</button>
    <button type="button" class="btn btn-info">info</button>
    <button type="button" class="btn btn-warning">warning</button>
  </div>
</template>
<script>
export default{
  name:'HelloWorld',
  props:{
    msg: String 
  }
}
</script>
<style scoped>
</style>