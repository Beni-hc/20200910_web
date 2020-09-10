<template>
    <ul>
        <Item v-for='(todo,index) in todos' :key='todo.id' :todo='todo' :index='index' :delItem='delItem'/>
    </ul>
</template>

<script>
import Item from './Item.vue'
export default {
    props:['todos','delItem'],
    components:{
        Item,
    }
}
</script>

<style scoped>
ul {
    width: 476px;
    margin: 15px 0;
    padding: 0;
    border-left: 1px solid #c1c3c1;
    border-right: 1px solid #c1c3c1;
    border-top: 1px solid #dedfde;
}
</style>