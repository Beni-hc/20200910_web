<template>
    <div class='app'>
        <Header :addTodo='addTodo'/>
        <List :todos='todos' :delItem='delItem' />
        <Footer :todos='todos' :checkedCompleted='checkedCompleted' :delCompleted='delCompleted'/>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import List from './components/List.vue'
import Footer from './components/Footer.vue'
export default {
    data(){
        return {
            todos:[
                {id:1,title:'打代码A',completed:false},
                {id:2,title:'打代码B',completed:true},
                {id:3,title:'打代码C',completed:false}
            ]
        }
    },
    methods:{
        addTodo(todo){
            this.todos.unshift(todo)
        },
        delItem(index){
            this.todos.splice(index,1)
        },
        checkedCompleted(isChecked){
            this.todos.forEach(element => {
                element.completed = isChecked
            });
        },
        delCompleted(){

            for(let i = 0;i < this.todos.length ; i++){
                if(this.todos[i].completed){
                    this.todos.splice(i,1)
                    i--
                }
            }
            
        }
    },
    components:{
        Header,
        Footer,
        List,
    },
}
</script>

<style scoped>
.app {
    width: 500px;
    margin: 50px auto;
    box-sizing: border-box;
    border: 1px solid #c1c3c1;
    border-radius: 5px;
    padding: 10px;
}
</style>