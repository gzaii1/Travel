<template>
    <div class="wrapper">
        <swiper :options="swiperOption" >
            <swiper-slide v-for="item of list" :key="item.id">
                <img  
                :src="item.imgUrl" 
                class="swiper-img" >
            </swiper-slide>
            <div class="swiper-pagination swiper-up" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
    export default {
        name: 'HomeSwiper',
        props:{
            list:Array
        },
        data: function() {
            return {
                swiperOption: {
                    pagination:'.swiper-pagination',
                    loop:true
                },
            }
        }
    }
</script>

<style lang="stylus" scoped="scoped">
    .wrapper >>> .swiper-pagination-bullet-active
        background:#fff
    .wrapper
        overflow:hidden
        width:100%
        height:0
        padding-bottom:34.25%
        background : #eee
    .swiper-img 
        width:100%
        
        
</style>
