<template>
<Demo msg="测试" school="尚硅谷" @hello="showEmit">
<span>尚硅谷</span>
</Demo>
</template>

<script>



import Demo from './components/Demo'
export default {
  name: 'App',
  components: { Demo },
  setup() {
    function showEmit(value) {
      alert(`触发了showEmit,收到的参数是${value}`)
    }
    return {
      showEmit
    }
  }
}
</script>

<style>

</style>
