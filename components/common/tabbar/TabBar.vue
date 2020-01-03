<template>
    <div id="TabBar">
       <tab-bar-item path='/' inactiveColor='#999' activeColor='pink'>
           <div class="item-text" slot='item-text'>首页</div>
       </tab-bar-item>
        <tab-bar-item  path='/category' inactiveColor='#999' activeColor='pink'>
           <div  class="item-text"  slot='item-text'>分类页</div>
       </tab-bar-item>
        <tab-bar-item path='/shop' inactiveColor='#999' activeColor='pink'>
           <div  class="item-text"  slot='item-text'>购物车</div>
       </tab-bar-item>
        <tab-bar-item path='/user' inactiveColor='#999' activeColor='pink'>
           <div  class="item-text"  slot='item-text'>个人</div>
       </tab-bar-item>
    </div>
</template>

<script>
import TabBarItem from './TabBarItem'
export default {
    name:"TabBar",
    components:{
        TabBarItem
    }
}
</script>

<style lang='scss' scoped>
    #TabBar{
        display: flex;
        position: fixed;
        left: 0;
        bottom: 0;
        right: 0;
        height: 49px;
        line-height: 49px;
        background: #f6f6f6;
        box-shadow: 0 -1px 1px rgba(100,100,100,.2);
        box-sizing: border-box;
    }
</style>