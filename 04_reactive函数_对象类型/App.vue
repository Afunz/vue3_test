<template>
  <h1>个人信息</h1>
  <h2>姓名:{{person.name}}</h2>
  <h2>年龄:{{person.age}}</h2>
  <h2>工作类型:{{person.job.type}}</h2>
  <h2>工资:{{person.job.salary}}</h2>
  <h2>爱好:{{person.hobby}}</h2>
  <button @click="changeInfo">修改人员信息</button>
 
</template>

<script>
// import { h } from 'vue'
import { reactive } from 'vue'


export default {
  name: 'App',
  setup() {
    let {person}= reactive(
      {
        person:  {
        name:'张三',
        age : 18,
        job :{
        type: "前端工程师",
        salary:"10K"
        },
        hobby:['打游戏','吃饭']
    }
      }
    )

    function changeInfo() {
      person.name = "李四"
      person.age= 48
     
      person.job.type="UI设计师"
      person.job.salary = "8k"
      person.hobby[0] = "睡觉"
       
    }

   return{
    person,
    changeInfo
   } 
  // return ()=>h('h1','尚硅谷')
  }  
}
</script>

<style>

</style>
