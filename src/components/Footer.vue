<template>
    <div>
        <input type="checkbox" v-model="isChecked">
        <span>已完成{{completed}} / 全部{{todos.length}}</span>
        <button v-show="todos.length>0" @click='delCompleted'>清除已完成任务</button>
    </div>
</template>

<script>
export default {
    props:{
        todos:Array,
        checkedCompleted:Function,
        delCompleted:Function
    },
    data(){
        return {
           
        }
    },
    computed:{
        completed(){
            return (this.todos.filter((todo) => todo.completed)).length
        },
        isChecked:{
            get(){
                return this.todos.length === this.completed && this.todos.length > 0
            },
            set(value){
                this.checkedCompleted(value)
            }
            
        }
    }
    
   
    
}
</script>

<style scoped>
    div {
        width: 478px;
        height: 30px;
        position: relative;
        top: 0;
        left: 0;
        line-height: 30px;
      
    }
    div button {
        height: 27px;
        width: 120px;
        position: absolute;
        right: 0;
        top: 0;
        bottom: 0;
        margin: auto 0;
        color: #fdfefd;
        background-color: #e55b45;
        border-radius: 5px;
        font-size: 14px;
        border: 1px solid #e55b45;
        outline-style: none;
    }
    div input {
        width: 11px;
        height: 11px;
        margin: 0 8px;
    }
    div span {

        font-size: 14px;
    }
</style>