<template>
    <div class="list" ref="wrapper">
        <div >
        <div class="area">
            <div class="title border-topbottom">当前城市</div>
            <div class="button-list">
                <div class="button-wrapper">
                    <div class="btn">{{this.currentCity}}</div>
                </div>
            </div>
        </div>
        <div class="area">
            <div class="title border-topbottom">热门城市</div>
            <div class="button-list">
                <div 
                    class="button-wrapper" 
                    v-for="item of hot" 
                    :key="item.id"
                    @click="handleCityClick(item.name)">
                    <div class="btn">{{item.name}}</div>
                </div>
            </div>
        </div>
        <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
            <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-bottom" 
                        :key = "innerItem.id"
                        v-for = "innerItem of item"
                        @click = "handleCityClick(innerItem.name)"
                        >{{innerItem.name}}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Bscroll from 'better-scroll'
    import {mapState,mapMutations} from 'vuex'
    export default {
        name: 'CityList',
        mounted (){
            this.scroll=new Bscroll(this.$refs.wrapper)
        },
        props:{
            hot:Array,
            cities:Object,
            letter:String
        },
        watch:{
            letter:function(){
                if(this.letter){
                    const element = this.$refs[this.letter][0]
                    this.scroll.scrollToElement(element)
                }
            }
        },
        methods:{
            handleCityClick (city){
                this.changeCity(city)
                this.$router.push('/')
            },
            ...mapMutations(['changeCity'])
        },
        computed:{
            ...mapState({
                currentCity:'city'
            })
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
        padding-left:15px
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
            padding-left:20px
</style>
