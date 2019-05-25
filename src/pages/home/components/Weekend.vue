<template>
    <div>
        <div class="recommend-title">想去哪玩</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img :src="item.imgUrl" class="item-img">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'HomeWeekend',
        data () {
            return {
            recommendList:[
                {
                    id : '0001',
                    imgUrl : 'http://img1.qunarzz.com/sight/source/1505/9f/f585152825459.jpg_r_640x214_5d46e4cc.jpg',
                    title:'大连圣亚海洋世界',
                    desc:'浪漫大连首站，浪漫的海洋主题乐园'
                },
                {
                    id : '0002',
                    imgUrl : 'http://img1.qunarzz.com/sight/source/1505/9f/f585152825459.jpg_r_640x214_5d46e4cc.jpg',
                    title:'大连圣亚海洋世界',
                    desc:'浪漫大连首站，浪漫的海洋主题乐园'
                },
                {
                    id : '0003',
                    imgUrl : 'http://img1.qunarzz.com/sight/source/1505/9f/f585152825459.jpg_r_640x214_5d46e4cc.jpg',
                    title:'大连圣亚海洋世界',
                    desc:'浪漫大连首站，浪漫的海洋主题乐园'
                }
            ]}
        }
    }
</script>

<style lang="stylus" scoped="scoped">
    @import '~styles/mixins.styl'
    .recommend-title
        margin-top :8px
        line-height:32px
        background:#eee
        text-indent:8px
    .item-img-wrapper
        overflow : hidden
        height:0
        padding-bottom:33.9%
    .item-img
        width:100%
       .item-info
            flex:1
            padding:6px
            min-width:0
            .item-title
                line-height:25px
                font-size:16px
                ellipsis()
            .item-desc
                line-height:20px
                color:#ccc
                ellipsis()
</style>
