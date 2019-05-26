<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
            </div>
        <div class="header-input"> 
            <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
        </div>
        <router-link to="/city">
            <div class="header-right">
                {{this.city}}<span class="iconfont arrow-icon">&#xe64a;</span>
            </div>
        </router-link>
    </div>
</template>

<script>
    import {mapState} from 'vuex'
    export default {
        name: 'HomeHeader',
        computed:{
            ...mapState(['city'])
        }
    }
</script>

<style lang="stylus" scoped="scoped">
    @import '~styles/varibles.styl'
    .header
        display:flex
        height:42px
        background:$bgColor
        color:#fff
    .header-left
        margin-top:11px
        margin-left:5px
        width:35px
        line-height:21px
        float:left
        .back-icon
            text-align:center
            font-size:20px
    .header-input
        height:33px
        line-height:33px
        margin-top:5px
        margin-right:10px
        padding-left:10px
        flex:1
        background:#fff
        border-radius:5px
        color:#ccc
    .header-right
        margin-top:11px
        margin-right:10px
        min-width:20px
        float:right
        text-align:center
        color:#fff
        .arrow-icon
            margin-left:5px
            font-size:5px
            margin-bottom:8px
</style>
