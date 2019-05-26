<template>
    <div>
        <div class="recommend-title">想去哪玩</div>
        <ul>
            <li class="item border-bottom" v-for="item of list" :key="item.id">
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
        props:{
            list :Array
        }
    }
</script>

<style lang="stylus" scoped="scoped">
    @import '~styles/mixins.styl'
    .recommend-title
        line-height:32px
        background:#eee
        text-indent:8px
    .item-img-wrapper
        overflow : hidden
        height:0
        padding-bottom:37.09%
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
