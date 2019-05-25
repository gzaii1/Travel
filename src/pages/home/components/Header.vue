<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
            </div>
        <div class="header-input"> 
            <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
        </div>
        <div class="header-right">
            城市<span class="iconfont arrow-icon">&#xe64a;</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HomeHeader'
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
        width:3rem
        float:right
        text-align:center
        .arrow-icon
            margin-left:5px
            font-size:5px
            margin-bottom:8px
</style>
