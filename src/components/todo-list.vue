<template>
    <div>
        <h1>Your ToDo List:</h1>
        <input type="text" name="todo" id="todo" placeholder="What's need to be done?" v-model="newTodo" @keydown.enter="addTodo" >
        <div class="todo-con">
            <div class="circle">
            


            
        <ul v-for="(todo,index) in todos" :key="todo.id" class="todo-items" >
            <div v-if="!todo.editing" class="todo-item"  >
                <div @dblclick="editTodo(todo)" >
                    <div class="each-item">
                    <input id="check" type="checkbox" name="check" v-model="todo.completed" >

                    <span class="each" :class="{ completed : todo.completed }">
                {{ todo.title }} 
            </span>
        </div>
                </div>
                <span class="remove-item" @click="removeTodo(index)" > &times; </span> 
            </div>

            <div v-else >
                <input v-model="todo.title" class="edit" @dblclick="doneEditing(todo)" @keypress.enter="doneEditing(todo)" type="text" >
            </div>

            
               
          
            

        </ul>
    </div>

        <div class="extra-container">
            <hr>

                
               
<input type="checkbox" name="check"> 
check All
</div>




</div>
        
        

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
        },
        


        
    }
}
</script>

<style>

    #todo {
        padding: 10px 30px;
        margin-bottom: 20px;
    }
    body {
        background: rgba(0, 0, 0, 0.185);
    }
    #check {
        width: 15px;
        position: absolute;
        left: 10px;
    }
    .todo-con {
        background: rgba(0, 128, 0, 0.397);
        border-radius: 15px;
        padding: 10px;
        margin: auto;
        width: 500px;
        max-height: 500px;
        overflow: auto;
        position: relative;
    }
    .th3 {
        
        margin-left: 150px;
        
       
    }
    .tr-flex {
        display: flex;
        justify-content: space-between;
    }
    .remove-item {
        cursor: pointer;
        
        position: absolute;
        right: 10px;

    }
    .todo-item {
        display: flex;
        margin:auto;
        justify-content: space-between;
        
       
    }
    .completed {
        text-decoration: line-through;
        color: grey;
    }
    .each-item {
        width: 200;
    }
    .each {
        color: white;
        font-weight: bold;
        position: absolute;
        left: 50px;
        
    }
    .circle {
        background: rgba(255, 0, 0, 0.534);
        border-radius: 100%;
    }

</style>