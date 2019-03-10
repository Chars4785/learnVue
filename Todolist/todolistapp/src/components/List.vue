<style>
*{
    box-sizing:border-bos;

}
ul{
    margin:0;padding:0;
}
ul li{
    cursor:pointer; position: relative; padding: 8px 8px 8px 40px;
    background: #eee; font-size: 14px; transition: 0.2s;
    -webkit-uiser-select:none; -moz-user-select:none;
    -mu-user-select:none;user-select: none;
}
ul li:hover{
    background: #ddd;
}
ul li.checked{
    background :#888;
    color: #fff;
    text-decoration: line-through;
}

ul li.checked::before{
    content: '';position: absolute; border-color: #fff;
    border-style: solid; border-width: 0px 1px 1px 0px;
    top: 10px; left: 16px ; transform: rotate(45deg);
    height:8px; width: 8px;
}
</style>

<template>
    <ul id="todolist">
        <li  v-for="(a,index) in todolist" v-bind:key="checked(a.done)"
        v-on:click="donToggle(index)">
        <span>{{a.todo}}</span>
        <span v-if="a.done">완료</span>
        <span class="close"  v-on:click.stop="deleteTodo(index)">&#x00D7;</span>
        </li>
    </ul>

</template>

<script>

import event from './EventBus.vue';


export default {
    created: function(){
        event.$on('add-todo',this.addTodo);
    },
    data :function(){
        return {
            todolist:[
                {todo : "영화보기",done:false},
                {todo : "주말 산책",done:true},
                {todo : "ES6 학습",done:false},
                {todo : "영화보기",done:false},
            ]
        }
    },
    methods :{
        checked:function(done){
            if(done)
            return{
                checked:true
            };
            else return {
                checked: false
            };
        },
        addTodo:function(todo){
            if(todo !=""){
                this.todolist.push({todo:todo,done:false});
            }
        },
        donToggle:function(){
            this.todolist[index].done =! this.todolist[index.done];
        },
        deleteTodo : function(index){
                this.todolist.splice(index,1);
        }
    }
}
</script>
