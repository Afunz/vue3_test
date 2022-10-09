<template>
  <h1>求和:{{sum}}</h1>
  <button @click="sum++">加一</button>
  <hr>
  <h1>当前鼠标点击的坐标是:X:{{point.x}},Y:{{point.y}}</h1>
</template>

<script>
// import { h } from 'vue'
import { ref } from 'vue'
import usePoint from '../hooks/usePoint'

export default {
  name: 'Demo',
  setup() { 
    let sum = ref(0)
    let point=usePoint()
    return {
      sum,
      point
    }
  },

  // return ()=>h('h1','尚硅谷')
  
}
</script>

<style>

</style>
