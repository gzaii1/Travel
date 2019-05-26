<template>
    <ul class="list">
    	<li 
            class="item" 
            v-for="item of letters" 
            :key="item" 
            @click="handleLetterClick"
            @touchstart="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
            :ref="item"
            >{{item}}</li>
    </ul>
</template>

<script>
    export default {
        name: 'CityAlphabet',
        props:{
            cities:Object
        },
        data(){
            return {
                touchStatus:false,
                startY : 0,
                timer:null
            }
        },
        updated:function(){
            this.startY = this.$refs['A'][0].offsetTop
        },
        methods:{
            handleLetterClick (e){
                this.$emit('change',e.target.innerHTML)
            },
            handleTouchStart(){
                this.touchStatus = true
            },
            handleTouchMove(e){
                if(this.touchStatus){
                    if(this.timer){
                        clearTimeout(this.timer)
                    }
                    this.timer = setTimeout(()=>{
                        const touchY = e.touches[0].clientY - 78
                        const index = Math.floor((touchY-this.startY)/21)
                        if(index >=0 && index <this.letters.length+1){
                            this.$emit('change',this.letters[index-1])
                        }
                    },16)
                }
            },
            handleTouchEnd(){
                this.touchStatus = false
            }
        },
        computed:{
            letters(){
                const letters = []
                for(let i in this.cities){
                   letters.push(i) 
                }
                return letters
            }
        }
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
