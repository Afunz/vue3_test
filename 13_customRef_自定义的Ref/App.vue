<template>
 <input type="text" v-model="keyWord">
 <h3>{{keyWord}}</h3>
</template>

<script>


import { ref,customRef } from 'vue';

export default {
  name: 'App',
  setup() { 
    function myRef(value,delay) {
      let timer
      return customRef((track,trigger) => { 
        return {
          get() { 
            console.log(`有人读取了keyWord的值,keyWord的值为${value}`);
            track()
            return value
          },
          set(newValue) { 
            console.log(`有人修改了keyWord的值,keyWord的值为${newValue}`);
            clearTimeout(timer)
            timer=setTimeout(() => {
            value = newValue
            trigger()
           }, delay);
          }
        }
      })
    }
    let keyWord = myRef('hello',500)
    return {keyWord}
  }
}
</script>

<style>

</style>
