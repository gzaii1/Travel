<template>
    <div>
        <div class="search">
           <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
           <ul>
               <li v-for="item of list" class="search-item border-bottom" :key="item.id">
                   {{item.name}}
               </li>
               <li class="search-item border-bottom" v-show="!list.length">没有找到匹配数据</li>
           </ul> 
        </div>
    </div>
</template>

<script>
    import Bscroll from 'better-scroll'
    export default {
        name: 'CitySearch',
        props:{
            cities:Object
        },
        data(){
            return{
                keyword:'',
                list:[],
                timer:null
            }
        },
        watch:{
            keyword(){
                if(this.timer){
                    clearTimeout(this.timer)
                }
                if(!this.keyword){
                    this.list = []
                    return 
                }
                this.timer = setTimeout(()=>{
                    const result = []
                    for(let i in this.cities){
                        this.cities[i].forEach((value)=>{
                            if(value.spell.indexOf(this.keyword)>-1 ||value.name.indexOf(this.keyword)>-1 ){
                                result.push(value)
                                }
                        })
                    }
                    this.list = result
                },100)
            }
        },
        mounted:function(){
            this.scroll = new Bscroll(this.$refs.search)
        }
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
    .search-content
        z-index:1
        overflow:hidden
        position:absolute
        top:88px
        left:0
        right:0
        bottom:0
        background:#eee
        .search-item
            line-height:31px
            padding-left:10px
            background:#fff
            color:#666
</style>
