<template>
  <div id="home">
    <nav-bar class="nav-bar"><div slot='center'>Nuxt-Mall</div></nav-bar>
    <home-swiper :banners='banners'></home-swiper>
    <tab-control :title="controlTitle" @tabClick='tabClick'></tab-control>
    <good-list :goodsList='goodList'></good-list>
    <!-- <h1>{{goodList}}</h1> -->
  </div>
</template>

<script>
import NavBar from '~/components/common/navbar/NavBar'
import HomeSwiper from '~/components/home/HomeSwiper'
import TabControl from '~/components/home/TabControl'
import GoodList from '~/components/home/GoodList'
import {getHomeMultidata,getHomeData} from '~/network/home'
export default {
  name:'index',
  data(){
    return{
      controlTitle:['流行','新款','精选'],
      currentType:'pop'
    }
  },
  async asyncData(){
    const HomeMultidata=await getHomeMultidata();
    const HomeData=await getHomeData('pop',1);
    return {
      banners:HomeMultidata.data.banner.list,
      goodList:HomeData.data.list
    }
  },
  components: {
    NavBar,
    HomeSwiper,
    TabControl,
    GoodList
  },
  created(){
    console.log(this.goodList);
  },
  methods:{
    tabClick(index){
      switch(index){
        case 0:
          this.currentType='pop'
          break;
        case 1:
          this.currentType='new'
          break;
        case 2:
          this.currentType='sell'
          break;
      }
    }
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
