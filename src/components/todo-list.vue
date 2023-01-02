<template>
    <div>
        <h1>Your ToDo List:</h1>
        <input type="text" name="todo" id="todo" placeholder="What's need to be done?" v-model="newTodo" @keydown.enter="addTodo" >
        
        <ul v-for="(todo,index) in todos" :key="todo.id" class="todo-item" >
            <div class="todo-item"  >
                {{ todo.title }} <span class="remove-item" @click="removeTodo(index)" > &times; </span> 
            </div>

            <div >
                <input v-model="todo.title" class="edit" @dblclick="inputtodo" type="text" >
            </div>
               
          
            

        </ul>
        
        

    </div>
</template>

<script>





export default {
    components: { 

    },
    name:'todo-list',
    data() {
        return {
            newTodo: '',
            todoid: 1,
            todos: [
                {
                    'id':0,
                    'title': 'Have to go',
                    'completed' : false,
                },
                
            ]
        }
    },
    methods: {
        addTodo() {
            this.todos.push({
                id:this.todoid,
                title: this.newTodo,
                completed: false,
                
            })
            this.newTodo = '',
            this.todoid++

            console.log(this.todos);
        
        },

        removeTodo(index) {
            this.todos.splice(index, 1)


        },
        editTodo() {
            true
        }


        
    }
}
</script>

<style>
    #todo {
        padding: 10px 30px;
    }
    .remove-item {
        cursor: pointer;
    }

</style>