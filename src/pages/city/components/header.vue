<template>
    <div class="header">
        城市选择
        <router-link to="/">
            <div class="iconfont header-back">&#xe624;</div>
        </router-link>
    </div>
</template>

<script>
    export default {
        name: 'CityHeader',
    }
</script>

<style lang="stylus" scoped="scoped">
    @import '~styles/varibles.styl'
    .header
     position:relative
     overflow:hidden
     height:42px
     line-height:42px
     text-align:center
     color:#fff
     background:$bgColor
     font-size:17px
     .header-back
        position:absolute
        top:0
        left:0
        width:34px
        text-align:center
        font-size:20px
        color:#fff
</style>
