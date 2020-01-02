<template>
  <div id="home">
    <nav-bar class="nav-bar"><div slot='center'>Nuxt-Mall</div></nav-bar>
    <home-swiper :banners='banners'></home-swiper>
  </div>
</template>

<script>
import NavBar from '~/components/common/navbar/NavBar'
import HomeSwiper from '~/components/home/HomeSwiper'
import {getHomeMultidata,getHomeData} from '~/network/home'


export default {
  name:'index',
  data(){
    return{
      banners:[]
    }
  },
  asyncData(){
    return getHomeMultidata().then(res=>{
      return {
        banners:res.data.banner.list
      }
      
    })
  },
  created(){
  },
  components: {
    NavBar,
    HomeSwiper
  }
}
</script>

<style lang='scss'>
#home{
  .nav-bar{
    background: pink;
    color: #fff;
    font-weight: bold;
    font-size: 22px;
  }
}


</style>
