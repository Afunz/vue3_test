<template>
  <h1>个人信息</h1>
  <h2>{{name}}</h2>
  <h2>{{age}}</h2>
  <h2>{{sex}}</h2>
  <button @click="sayHello">说话(Vue3)</button>
  <button @click="sayWelcome">说话(Vue2)</button>
</template>

<script>
// import { h } from 'vue'



export default {
  name: 'App',
  data () {
    return {
      sex:'男'
    }
  },
  methods: {
    sayWelcome(){
      alert(`这个人的姓名为${this.name},年龄为${this.age},性别为${this.sex}`)
    }
  },
  setup() {
    let name='张三'
    let age=18

    function sayHello() {
      alert(`这个人的姓名为${name},年龄为${age}`)
    }

   return{
    name,
    age,
    sayHello
   } 
  // return ()=>h('h1','尚硅谷')
  }  
}
</script>

<style>

</style>
