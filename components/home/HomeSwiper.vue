<template>
    <div v-swiper:mySwiper="swiperOption">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="(banner,index) in banners" :key="index">
                 <a :href="banner.link">
                     <img :src="banner.image" :alt="banner.title">
                </a>
             </div>
         </div>
         <div class="swiper-pagination"></div>
     </div>
</template>
<script>
export default {
    name:'HomeSwiper',
    props:['banners'],
    data(){
        return{
            swiperOption:{
                loop:true,
                pagination:{
                    el:'.swiper-pagination'
                }
            }
        }
    }
}
</script>

<style lang="scss">  
.swiper-container{background: pink;font-size: 0; touch-action: none;}
.swiper-slide img{
    width: 100%; 
}
.swiper-pagination-bullet-active{
    background: pink;
}
</style>