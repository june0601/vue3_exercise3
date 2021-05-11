<template>
  <Parent />
  <hr>
  <ProductList />
  <hr>
  <SimpleCalculator />
   <hr>
  <div class="home">
    <Head ref='Head'></Head>
    <span>我是主要部分</span>
  </div>
  <hr>
  <div>
    <h2 @click="changeName">{{name}}</h2>
    <h2 @click="add">3+6 = {{num}}</h2>
  </div>
  <hr>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Parent from '@/components/Parent'
import ProductList from '@/components/ProductList'
import SimpleCalculator from '@/components/SimpleCalculator'
import Head from '@/components/head.vue'
import Common from '@/components/common'
export default {
  name: 'App',
  data () {
    return {
      name: Common.userName,
      num: Common.add(3,6)
    }
  },
  components: {
    //HelloWorld
    Parent,
    ProductList,
    SimpleCalculator,
    Head,
  },
  mounted () {
    alert(this.$refs.Head.msg)
    this.$refs.Head.msg = '正在呼叫子元件'
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.home{
  width: 100%;
  height: 500px;
  background-color: antiquewhite;
}
</style>
