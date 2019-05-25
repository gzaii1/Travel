<template>
    <div class="wrapper">
        <swiper :options="swiperOption" >
            <swiper-slide v-for="item of swiperList" :key="item.id">
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
        data: function() {
            return {
                swiperOption: {
                    pagination:'.swiper-pagination',
                    loop:true
                },
                swiperList:[{
                    id:'0001',
                    imgUrl:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1558797357041&di=0ce55b5cdb2adbc1c0939c66f4d5e640&imgtype=0&src=http%3A%2F%2Fimg.mp.itc.cn%2Fupload%2F20170820%2Fc9163b49ad9141f385cd33abdc8b479d.jpg'
                },{
                    id:'0002',
                    imgUrl:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1558802590913&di=24e786a7c0d2e2dac055f37895297382&imgtype=0&src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fimages%2F20180821%2F92e9d46177874103a0f417b519943e32.jpeg'
                },{
                    id:'0003',
                    imgUrl:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1558802610466&di=675f21d1746646f4c14022a57be27d96&imgtype=0&src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fimages%2F20170913%2F3bdaea5412f84ae8a194135a0633b553.jpeg'
                }]
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
