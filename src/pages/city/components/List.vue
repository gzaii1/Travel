<template>
    <div class="list" ref="wrapper">
        <div >
        <div class="area">
            <div class="title border-topbottom">当前城市</div>
            <div class="button-list">
                <div class="button-wrapper">
                    <div class="btn">北京</div>
                </div>
            </div>
        </div>
        <div class="area">
            <div class="title border-topbottom">热门城市</div>
            <div class="button-list">
                <div class="button-wrapper">
                    <div class="btn">北京</div>
                </div>
                <div class="button-wrapper">
                    <div class="btn">北京</div>
                </div>
                <div class="button-wrapper">
                    <div class="btn">北京</div>
                </div>
                <div class="button-wrapper">
                    <div class="btn">北京</div>
                </div>
                <div class="button-wrapper">
                    <div class="btn">北京</div>
                </div>
            </div>
        </div>
        <div class="area">
            <div class="title border-topbottom">A</div>
                <div class="item-list">
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                </div>
        </div>
        
        <div class="area">
            <div class="title border-topbottom">A</div>
                <div class="item-list">
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                </div>
        </div>
        
        <div class="area">
            <div class="title border-topbottom">A</div>
                <div class="item-list">
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Bscroll from 'better-scroll'
    export default {
        name: 'CityList',
        mounted (){
            this.scroll=new Bscroll(this.$refs.wrapper)
        }
    }
</script>

<style lang="stylus" scoped="scoped">
    @import '~styles/varibles.styl'
    .border-topbottom
        &:before
            border-color:#ccc
        &:after
            border-color:#ccc
    .border-bottom
        &:before
            border-color:#ccc
        &:after
            border-color:#ccc
   .list
         overflow:hidden   
         position:absolute
         top:87px
         left:0
         right:0
         bottom:0
    .title
        line-height:22px
        background:#eee
        padding-left:1px
        color:#666
        font-size:13px
    .button-list
        overflow:hidden
        padding:5px
    .button-wrapper
        float:left
        width:33.33%
    .btn
        margin:5px
        padding:5px 0
        text-align:center
        border:1px solid #ccc
        border-radius:3px
    .item-list
        .item
            line-height:38px
            padding-left:1px
</style>
