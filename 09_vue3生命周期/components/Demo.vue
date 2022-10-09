<template>
  <h1>求和:{{sum}}</h1>
  <button @click="sum++">加一</button>
</template>

<script>
// import { h } from 'vue'
import { ref,onBeforeMount,onMounted,onBeforeUpdate,onUpdated,onBeforeUnmount,onUnmounted } from 'vue'


export default {
  name: 'Demo',
  setup() { 
    console.log('--setup--');
    let sum = ref(0)
    onBeforeMount(() => {
      console.log('--onBeforeMount--');
    })
    onMounted(() => {
      console.log('--onMounted--');
    })
    onBeforeUpdate(() => {
      console.log('--onBeforeUpdate--');
    })
    onUpdated(() => {
      console.log('--onUpdated--');
    })
    onBeforeUnmount(() => {
      console.log('--onBeforeUnmount--');
    })
    onUnmounted(() => {
      console.log('--onUnmounted--');
    })
    return {
      sum,
    }
  },
/*   beforeCreate() {
    console.log('--beforeCreate--');
  },
  created() {
    console.log('--created--');
  },
  beforeMount() { 
    console.log('--beforeMount--');
  },
  mounted() {
    console.log('--mounted--');
  },
  beforeUpdate() {
    console.log('--beforeUpdate--');
  },
  updated() {
    console.log('--updated--');
  },
  beforeUnmount() {
    console.log('--beforeUnmount--');
  },
  unmounted() { 
    console.log('--unmounted--');
  } */
  // return ()=>h('h1','尚硅谷')
  
}
</script>

<style>

</style>
