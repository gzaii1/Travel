<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
                <router-link 
                    tag="li"
                    class="item border-bottom" 
                    v-for="item of list" 
                    :key="item.id"
                    :to="'/detail/'+item.id">
                    <img :src="item.imgUrl" class="item-img">
                    <div class="item-info">
                        <p class="item-title">{{item.title}}</p>
                        <p class="item-desc">{{item.desc}}</p>
                        <button class="item-btn" >查看详情</button>
                    </div>
                </router-link>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'HomeRecommend',
        props:{
            list :Array
        },
        data () {
            return {}
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
                    border-radius:5px !important
                    box-shadow:none !important
                    color:#fff
                    
</style>
