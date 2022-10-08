<template>
  <h1>个人信息</h1>
  <h2>姓名:{{person.name}}</h2>
  <h2>年龄:{{person.age}}</h2>
  <h2>{{msg}}</h2>
  <h2>{{school}}</h2>
  <button @click="test">测试一下Demo组件的内容</button>
  <slot></slot>
</template>

<script>
// import { h } from 'vue'
import { reactive } from 'vue'


export default {
  name: 'Demo',
  props: ['msg', 'school'],
  emits: ['hello'],
  setup(props, context) {
    console.log('--setup--',props);
    console.log('--setup--',context);
    let {person}= reactive(
      {
        person:  {
        name:'张三',
        age : 18,
    }
      }
    )
    function test() {
      context.emit('hello',666)
    }
   return{
     person,
     test
   } 
  // return ()=>h('h1','尚硅谷')
  }  
}
</script>

<style>

</style>
