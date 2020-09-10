<template>
    <input type="text" placeholder='请输入你的任务名称，按回车键确认' @keyup.enter='add' v-model="title">
</template>

<script>
export default {
    props:{
        'addTodo':Function
    },
    data(){
        return {
            title:''
        }
    },
    methods:{
        add(){
            const title = this.title.trim()
            if(!title) return 
            const todo ={
                id: Date.now(),
                title,
                completed:false
            }
            this.addTodo(todo)
            this.title = ''
        }
    }
    
}
</script>

<style scoped>
input {
    width: 460px;
    height: 20px;
    border-radius: 4px;
    border: 1px solid #dbdcdb;
    margin: 0;
    padding: 8px;
    outline-color: rgb(97, 228, 233);
    font-size: 14px;
}
</style>