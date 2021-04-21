<template>
    <!-- Rendu de la liste de tâche -->
    <div class="task" v-for="newTask in tasks" :key="newTask">
        <input type="checkbox">
       <ul>
           <!-- Affichage de la tâche entrée dans l'input -->
           <li>{{newTask.taskName}}</li>
       </ul>
       <!-- Event on click qui supprime la tâche -->
       <button :click="deleteTask" :key="newTask" @click="deleteEvent(newTask)"><i class="fas fa-trash-alt"></i></button>
    </div>
</template>

<script>
export default {
    name: 'todoList',
    // Ajout de types devaleur sur les propriétés
    props : {
        tasks : {
            type : Array
        },
        taskName : {
            type : String
        },
    },

    // Permet de récupérer les données d'un fichier parent
    methods: {
        deleteEvent(check){
            this.$emit('deleteTodo', check);
        }
    }   
}
</script>

<style scoped>
.task{
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 10px 0;
}

input[type=checkbox] {
    width: 20px;
    height: 20px; 
 
}

button{
    background: transparent;
    border: none;
    color: red;
}

ul{
    width: 50%;
}
</style>