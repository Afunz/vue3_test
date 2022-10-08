<template>
  <h1>求和:{{sum}}</h1>
  <button @click="sum++">加一</button>
  <h1>{{msg}}</h1>
  <button @click="msg+='!'">加!</button>
  <h1>{{person.name}}</h1>
  <h1>{{person.age}}</h1>
  <h1>{{person.job.j1.salary}}K</h1>
  <button @click="person.name+='~'">修改姓名</button>
  <button @click="person.age++">修改年龄</button>
  <button @click="person.job.j1.salary++">涨薪</button>
</template>

<script>
// import { h } from 'vue'
import { ref,watch,reactive,watchEffect } from 'vue'


export default {
  name: 'Demo',
  setup() { 
    let sum = ref(0)
    let msg = ref('你好啊')
    let person = reactive({
      name: '张三',
      age: 18,
      job: {
        j1: {
          salary:20
        }
      }
    })
    watchEffect(() => { 
      const x1 = sum.value
      const x2 = person.job.j1.salary
      console.log("watchEffect函数被调用了");
    })
    return {
      sum,
      msg,
      person
    }
  }
  // return ()=>h('h1','尚硅谷')
  
}
</script>

<style>

</style>
