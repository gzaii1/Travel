<template>
    <div>
        <div 
            class="item" 
            v-for="(item,index) of list"
            :key="index">
            <div class="item-title border-bottom">
                <span class="item-title-icon"></span>
                {{item.title}}
            </div>
            <div v-if="item.children" class="item-children">
                <detail-list :list="item.children"></detail-list>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:'DetailList',
        props:{
            list:Array
        }
    }
    
</script>

<style lang="stylus" scoped="scoped">
    .item-title-icon
        display:inline-block;
        width:.65rem;
        height:.65rem;
        background:url(http://s.qunarzz.com/piao/image/touch/sight/detail.png)0-.0rem no-repeat;
        margin-right:.3rem;
        background-size:.8rem 6rem;
    .item-title
        line-height:40px
        font-size:16px
        padding:0 10px
    .item-children
        padding:0 10px
</style>
