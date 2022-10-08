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
import { ref,watch,reactive } from 'vue'


export default {
  name: 'Demo',
  setup() { 
    let sum = ref(0)
    let msg = ref('你好啊')
    let person = ref({
      name: '张三',
      age: 18,
      job: {
        j1: {
          salary:20
        }
      }
    })
  /*   watch(sum, (newValue, oldValue) => { 
      console.log('sum变了',newValue,oldValue);
    })
    watch(msg, (newValue, oldValue) => { 
      console.log('sum变了',newValue,oldValue);
    }) */
     /* watch([sum,msg], (newValue, oldValue) => {
       console.log('sum变了', newValue, oldValue);
     }, {immediate:true}) */
    watch(person, (newValue, oldValue) => { 
      console.log(person);
      console.log("person值改变了",newValue,oldValue);
    }, {deep:true})
  /*   watch(()=>person.name,(newValue, oldValue) => { 
      console.log("person.name值改变了",newValue,oldValue);
    })
    watch(()=>person.age,(newValue, oldValue) => { 
      console.log("person.age值改变了",newValue,oldValue);
    }) */
     /* watch([()=>person.name,()=>person.age],(newValue, oldValue) => { 
      console.log("person.name,age值改变了",newValue,oldValue);
     })
    watch(()=>person.job,(newValue, oldValue) => { 
      console.log("person.name,age值改变了",newValue,oldValue);
    }, {deep:true}) */
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
