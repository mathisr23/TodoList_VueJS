<template>
    <div class="new-todo">
        <!-- v-model qui utilise les propriétés de l'input -->
        <input name="add-todo" type="text" placeholder="Nouvelle tâche" v-model="newTask">
        <!-- Event on click qui ajoute la tâche -->
        <button v-on:click="addTask()" type="submit"><i class="fas fa-plus-circle"></i></button>
    </div>
</template>

<script>
export default {
    name: 'NewTodo', 
    data () {
        // Renvoi de la valeur entrée dans l'input
        return{
         newTask: ''
        }
    },
    // Permet de récupérer les données d'un fichier parent
    methods: {
        addTask(){
            this.$emit('taskName', this.newTask)
        }
    }
}
</script>

<style scoped>
.new-todo{
    display: flex;
    justify-content: center;
    align-items: center;
    padding-top: 20px;
}

input{
    text-align: center;
    border: none;
    padding: 10px;
    background-color: white;
    border-bottom: 2px solid #0AD3B5;
}
.fa-plus-circle{
    padding-left: 30px;
    font-size: 30px;
    color: #48C774;
}

button{
    background-color: transparent;
    border: none;
}
</style>