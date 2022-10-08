<template>
  <h1>个人信息</h1>
  <input type="text" v-model="person.firstname">
  <br><br>
  <input type="text" v-model="person.lastname">
  <br><br>
  <h3>{{person.fullname}}</h3>
  <br><br>
  <input type="text" v-model="person.fullname">
</template>

<script>
// import { h } from 'vue'
import { reactive,computed } from 'vue'


export default {
  name: 'Demo',
  // computed: {
  //   fullname() {
  //     return this.person.firstname+'-'+this.person.lastname
  //    }
  // },
  setup() {
    let {person}= reactive(
      {
        person:  {
        firstname:'张',
        lastname : '三',
        }
      }
    )
  /*   person.fullname =computed(() => {
      return person.firstname+'-'+ person.lastname
    }) */
    person.fullname = computed({
      get() { 
        return person.firstname+'-'+ person.lastname
      },
      set(value) { 
        const nameArr = value.split('-')
        person.firstname = nameArr[0],
        person.lastname=nameArr[1]
      }
    })
   return{
     person
   } 
  // return ()=>h('h1','尚硅谷')
  }  
}
</script>

<style>

</style>
