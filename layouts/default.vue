<template>
  <div>
    <nuxt keep-alive />
    <tab-bar></tab-bar>
  </div>
</template>

<script>
import TabBar from '~/components/common/tabbar/TabBar'
export default {
  components:{
    TabBar
  } 
}
</script>

<style>
html,body{
  width: 100%;
  height: 100%;
}
</style>
