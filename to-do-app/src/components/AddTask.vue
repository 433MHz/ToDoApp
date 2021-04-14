<template>
<div>
    <div id="container">
        Nowe todo:<br>
        <input type="text" placeholder="todo" v-model="titleText"><input type="button" value="Dodaj" v-on:click="AddNewTask(titleText)">
    </div><br>


    <div v-for="todoTask in todoTasks" :key="todoTask">
        <div id="container-todo">
            <h2 v-bind:class="{textdone: todoTask.done, textundone: todoTask.done === false}">{{todoTask.title}}</h2><br>
            <button v-if="todoTask.done === false" v-on:click="MakeDone(todoTask)">Zrobione</button>
        </div><br>
    </div>
</div>
</template>

<script>
export default {
    methods:{
        AddNewTask(title){
            this.todoTasks.push({title, done: false})
        },

        MakeDone(todoTask){
            todoTask.done = true
        }
    },
    data(){
        return{
            todoTasks:[
                {title:'Domyślny', done: false}
            ]
        }
    }
}
</script>


<style>
    #container{
        width: 400px;
        height: 70px;
        border: 3px solid gray;
        display: inline-block;
        text-align: left;
        padding-left: 15px;
        padding-top: 30px;
    }

    #container-todo{
        border: 3px solid gray;
        width: 415px;
        display: inline-block;
        margin-top: 10px;
    }

    ul{
        list-style-type: none;
    }

    .textdone{
        text-decoration: line-through;
        color: gray;
    }

    .textundone{
        text-decoration: none;
    }
</style>