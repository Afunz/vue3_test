<template>
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
import { ref,reactive,toRef,toRefs } from 'vue'


export default {
  name: 'Demo',
  setup() {
    let person = reactive({
      
      name: '张三',
      age: 18,
      job: {
        j1: {
          salary:20
        }
      }
    
    })

    return {
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
