<template>
    <ul class="list">
    	<li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
    </ul>
</template>

<script>
    export default {
        name: 'CityAlphabet',
    }
</script>

<style lang="stylus" scoped="scoped">
@import '~styles/varibles.styl'
    .list
        display: flex || inline-flex
        flex-direction:column
        justify-content:center
        position:absolute
        top:88px
        right:0
        bottom:0
        width:20px
        .item
            line-height:22px
            text-align:center
            color:$bgColor
</style>
