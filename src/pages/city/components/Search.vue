<template>
    <div class="search">
       <input class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
</template>

<script>
    export default {
        name: 'CitySearch',
    }
</script>

<style lang="stylus" scoped="scoped">
    @import '~styles/varibles.styl'
    .search
        position:relactive
        height:35px
        padding:5px
        background:$bgColor
        .search-input
            letter-spacing: -1px;px
            position:absolute
            width:99%
            height:30px
            line-height:30px
            text-align:center
            border-radius:5px !important
            color:#666
</style>
