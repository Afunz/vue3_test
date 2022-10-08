<template>
  <h1>个人信息</h1>
  <h2>姓名:{{name}}</h2>
  <h2>年龄:{{age}}</h2>
  <h2>工作类型:{{job.type}}</h2>
  <h2>工资:{{job.salary}}</h2>
  <button @click="changeInfo">修改人员信息</button>
 
</template>

<script>
// import { h } from 'vue'
import { ref } from 'vue'


export default {
  name: 'App',
  setup() {
    let name=ref('张三')
    let age = ref(18)
    let job = ref({
      type: "前端工程师",
      salary:"10K"
    })

    function changeInfo() {
      name.value = "李四"
      age.value = 48
      job.value.type="UI设计师"
      job.value.salary="8k"
    }

   return{
    name,
     age,
    job,
    changeInfo
   } 
  // return ()=>h('h1','尚硅谷')
  }  
}
</script>

<style>

</style>
