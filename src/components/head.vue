<template>
  <div class="head">
    <span>我是子元件</span>
    <span>{{msg}}</span>
  </div>
</template>

<script>
export default {
  name: 'Head',
  data () {
    return {
      msg: '我是頭部'
    }
  }
}
</script>

<style scoped>
.head{
  width: 100%;
  height: 200px;
  background-color: aqua;
}
</style>