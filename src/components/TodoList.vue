<template>
  <div>
    <input type="text" class="todo-input" 
    placeholder="Input your todo" v-model="newTodo" @keyup.enter="addTodo">
    <div v-for="(todo, index) in todos" :key="todo.id" class="todo-item">
        <div class="todo-item-left">
            <div v-if="!todo.editing" class="todo-item-label">{{ todo.title }}</div>
            <input class="todo-item-edit" type="text" v-model="todo.title">
        </div>
        <div class="remove-item" @click="removeTodo(index)">
            &times;
          

        </div>
    </div>
   </div>
  </template>
  
  <script>
  export default {
    name: 'todo-list',
    data () {
        return {
            newTodo:'',
            idForTodo: 3,
            todos: [
                {
                    'id':1,
                    'completed': false,
                    'title': 'Finish Vue App',
                    'editing': false,
                },
                {
                    'id':2,
                    'completed': false,
                    'title': 'Take Over World',
                    'editing': false,
                },
                {
                  'id':3,
                    'completed': false,
                    'title': 'Go to the saloon',
                    'editing': false,
                }
            ]
        }
    },
    methods: {
        addTodo  (){
            if (this.newTodo.trim().length == 0) {
                return
            }
            this.todos.push ({
                id: this.idForTodo,
                title: this.newTodo,
                completed: false,
            })
            this.newTodo = ''
            this.idForTodo ++

        },
        removeTodo(index) {
            this.todos.splice(index, 1)
        }

    }
  }
  </script>
  
  <style>
  
  .todo-input {
    width: 350px;
    padding: 10px 18px;
    font-size: 20px;
    font-style: italic;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    margin-bottom: 16px;
    text-align: center;
    display: inline;
    margin-left: 15px;
    

  }
  .todo-item {
    margin-bottom: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    
  }
  .remove-item {
    cursor: pointer;
    margin-left: 14px;
  }
  &:hover {
    color: black;
  }
  .todo-item-left {
    display: flex;
    align-items: center;
  }
  .todo-item-label {
    padding: 16px;
    margin-left: 12px;
    border: 1px solid white;
    /* background-color: rgb(11, 68, 3); */
    color: aqua;
    border-top-right-radius: 25px;
    border-bottom-left-radius: 25px;
    background-image: linear-gradient(to left bottom,green,white);

  }
  .todo-item-edit {
    font-size: 18px;
    color: #2c3e50;
    margin-left: 12px;
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    font-family: 'Avenir', Arial, Helvetica, sans-serif;
    background-color: lemonchiffon;
  }
  </style>
  