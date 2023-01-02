<template>
    <div>
        <h1>Your ToDo List:</h1>
        <input type="text" name="todo" id="todo" placeholder="What's need to be done?" v-model="newTodo" @keydown.enter="addTodo" >
        
        <ul v-for="(todo,index) in todos" :key="todo.id" class="todo-items" >
            <div v-if="!todo.editing" class="todo-item"  >
                <div @dblclick="editTodo(todo)" >
                {{ todo.title }} 
                </div>
                <span class="remove-item" @click="removeTodo(index)" > &times; </span> 
            </div>

            <div v-else >
                <input v-model="todo.title" class="edit" @dblclick="doneEditing(todo)" @keypress.enter="doneEditing(todo)" type="text" >
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
                    'editing': false,
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
        editTodo(todo) {
            todo.editing = true
            
           
        },
        doneEditing(todo) {
            todo.editing = false
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
        margin-left: 150px;
    }
    .todo-item {
        display: flex;
        margin:auto;
        justify-content: center;
    }

</style>