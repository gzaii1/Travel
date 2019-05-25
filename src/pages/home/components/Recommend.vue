<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img :src="item.imgUrl" class="item-img">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-btn">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'HomeRecommend',
        data () {
            return {
            recommendList:[
                {
                    id : '0001',
                    imgUrl : 'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_140x140_73fda71d.jpg',
                    title:'大连圣亚海洋世界',
                    desc:'浪漫大连首站，浪漫的海洋主题乐园'
                },
                {
                    id : '0002',
                    imgUrl : 'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_140x140_73fda71d.jpg',
                    title:'大连圣亚海洋世界',
                    desc:'浪漫大连首站，浪漫的海洋主题乐园'
                },
                {
                    id : '0003',
                    imgUrl : 'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_140x140_73fda71d.jpg',
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
    .item
        overflow:hidden
        display:flex
        height:94px
        border-bottom:0.4px #eee solid
        .item-img
            width:70px
            height:70px
            padding:6px
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
                .item-btn
                    margin-top:3px
                    background:#ff9300
                    padding:0 5px
                    border-radius:3px
                    color:#fff
</style>
