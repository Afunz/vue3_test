<template>
  <h1>个人信息</h1>
  <h2>{{name}}</h2>
  <h2>{{age}}</h2>
  <button @click="changeInfo">修改人员信息</button>
 
</template>

<script>
// import { h } from 'vue'
import { ref } from 'vue'


export default {
  name: 'App',
  setup() {
    let name=ref('张三')
    let age=ref(18)

    function changeInfo() {
      name.value = "李四"
      age.value=48
    }

   return{
    name,
    age,
    changeInfo
   } 
  // return ()=>h('h1','尚硅谷')
  }  
}
</script>

<style>

</style>
