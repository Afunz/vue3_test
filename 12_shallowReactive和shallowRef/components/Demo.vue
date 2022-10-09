<template>
  <h1>当前X的值为:{{x.y}}</h1>
  <button @click="x.y++">加一</button>
  <hr>
<h1>{{person}}</h1>
<h1>姓名:{{name}}</h1>
<h1>年龄:{{age}}</h1>
<h1>薪资:{{person.job.j1.salary}}K</h1>
<button @click="name+='~'">修改姓名</button>
<button @click="age++">增长年龄</button>
<button @click="person.job.j1.salary++">涨薪</button>
</template>

<script>
// import { h } from 'vue'
import { ref,reactive,toRef,toRefs,shallowReactive,shallowRef } from 'vue'


export default {
  name: 'Demo',
  setup() {
    //shallowReactive无法处理深层次的对象属性
    let person = shallowReactive({
      
      name: '张三',
      age: 18,
      job: {
        j1: {
          salary:20
        }
      }
    
    })
    //shallowRef基本数据类型与ref没差，但定义不了对象引用数据类型
    let x = shallowRef({
      y:0
    })
    return {
      x,
      person,
     /*  name: toRef(person, 'name'),
      age: toRef(person, 'age'),
      salary:toRef(person.job.j1,'salary') */
      ...toRefs(person)
    }
   }

  // return ()=>h('h1','尚硅谷')
  
}
</script>

<style>

</style>
