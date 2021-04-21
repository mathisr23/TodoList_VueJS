<template>
    <div class="todo-card">
        <nav>
            <ul>
                <!-- Format pour la date grâce à moment.js -->
                <li>{{moment().format("MMMM dddd Do YYYY")}}</li>
                <li>{{title}}</li>
                <!-- Affichage de la taille du tableau -->
                <li>Tâches : {{tasks.length}}</li>
            </ul>
        </nav>
        <new-todo @taskName="sendTask"/>
        <todo-list :tasks="tasks" @deleteTodo="deleteEvent"></todo-list>
    </div>
</template>
<script>

import moment from 'moment'
import newTodo from './new-todo.vue';
import TodoList from './TodoList.vue';



export default {
  components: { newTodo, TodoList },

    name: 'TodoCard',
    // Fonction pour afficher la date
    created: function () {
        this.moment = moment;
    },
    data () {
        return {
            title: "VueJS Tutorial ToDo List",
            tasks: [],
        }
    },

    methods: {
        // Fonction pour ajouter des tâches
        sendTask(newTask){
            this.tasks.push({
                taskName: newTask, 
                check: false,
            })
        },

        // Fonction pour supprimer des tâches
        deleteEvent(check){
            const deleteNb = this.tasks.indexOf(check);
            this.tasks.splice(deleteNb,1);
        },
    }
} 
</script>

<style scoped>
.todo-card{
    width: 1000px;
    height: 500px;
    background-color: white;
    border-radius: 10px;
    
}

.todo-card ul{
    display: flex;
    justify-content: space-around;
    font-weight: 500;
    padding: 10px 0;
    box-shadow: 0px 5px 15px ;
    
}

.todo-card ul li:nth-child(2){
 color: #0AD3B5;

}
</style>
