<template>
    <li @mouseenter="enterColor(true)" @mouseleave="enterColor(false)" :style='{backgroundColor:bgcolor}'>
        <input type="checkbox" v-model="todo.completed">
        <span>{{todo.title}}</span>
        <button @click='deltodo' v-show='isShow'>删除</button>
    </li>
    
</template>

<script>
export default {
    props:['todo','index','delItem'],
    data(){
        return {
            bgcolor: '#fff',
            isShow: false
            
        }
    },
    methods:{
        deltodo(){
            if(window.confirm(`确定删除${this.todo.title}吗？`)){
                this.delItem(this.index)
            } 
        },
        enterColor(isShow){
            if(isShow){
                this.bgcolor = '#eeeeee'
                this.isShow = isShow
            }else{
                this.bgcolor = '#fff'
                this.isShow = isShow
            }

        }
    }
    
}
</script>

<style scoped>
    li {
        list-style: none;
        width: 478px;
        height: 33px;
        position: relative;
        top: 0;
        left: 0;
        border-bottom: 1px solid #dedfde;
        line-height: 33px;
    }
    li input {
        width: 11px;
        height: 11px;
        margin: 0 8px;
    }
    li span {

        font-size: 16px;
    }
    li button {
        width: 60px;
        height: 25px;
        line-height: 25px;
        background-color: #e55b45;
        border-radius: 5px;
        font-size: 14px;
        color: #fdfefd;
        position: absolute;
        top: 0;
        right: 10px;
        bottom: 0;
        margin: auto 0;
        padding: 0;
        text-align: center;
        border: 1px solid #e55b45;
        outline:none
    }
</style>