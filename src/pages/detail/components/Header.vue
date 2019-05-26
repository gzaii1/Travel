<template>
    <div>
        <div class="header-abs">
            <div class="iconfont header-abs-back" @click="handleBackToHome">&#xe624;</div>
        </div>
        <div 
            class="header-fixed" 
            v-show="!showAbs"
            :style="opacityStyle">
             <router-link to="/">
                <div class="iconfont header-fixed-back">&#xe624;</div>
            </router-link>
            景点详情
        </div>
    </div>
</template>

<script>
    export default{
        name:'DetailHeader',
        methods:{
            handleBackToHome(){
                this.$router.push('/')
            },
             handleScroll(){
                const top = document.documentElement.scrollTop
                if(top >50 ||top <100){
                    const opacity = top/100
                    this.opacityStyle ={ opacity }
                    this.showAbs = false
                }else{
                    this.showAbs = true
                }
            }
        },
        data(){
            return{
                showAbs:true,
                opacityStyle:0,
                i:''
            }
        },
        mounted(){
            window.addEventListener('scroll',this.handleScroll)
        },
        beforeDestroy(){
            window.removeEventListener('scroll',this.handleScroll)
        }
    }
</script>

<style lang="stylus" scoped="scoped">
    @import '~styles/varibles.styl'
    .header-abs
        position:absolute
        left:10px
        top:10px
        width:40px
        height:40px
        line-height:40px
        border-radius:20px
        text-align:center
        background:rgba(0,0,0,0.8)
        .header-abs-back   
            color:#fff
            font-size:20px
     .header-fixed
         z-index:2
         position:fixed
         top:0
         left:0
         right:0
         height:42px
         line-height:42px
         text-align:center
         color:#fff
         background:$bgColor
         font-size:17px
         .header-fixed-back
            position:absolute
            top:0
            left:0
            width:34px
            text-align:center
            font-size:20px
            color:#fff
</style>
