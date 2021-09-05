<template>
<div id="containerButtonForm">
    <div id="addTask">
        <button v-on:click="seen =! seen">Nouvelle tâche</button>
    </div>
    <form id="form" ref="form" v-if="seen" @submit.prevent>
        <input type="name" ref="name" placeholder="Nom de tâche" v-model="name">

        <label for="dateStart">Début</label>
        <input type="date" ref="dateStart" v-model="start">

        <label for="dateEnd" ref="dateEnd">Fin</label>
        <input type="date" ref="dateEnd" v-model="end">

        <label for="dependance">Dépendant de :</label>
        <input type="text" ref="depencies" placeholder="Ecrire le nom d'une tâche" v-model="dependencies">

        <label for="progress">Progression</label>
        <input type="number" ref="progress" placeholder="Uniquement chiffre" v-model="progress">
        <div id="buttons">
            <button id="send" v-on:click="submitTask">Créer</button>
            <button id="cancel" v-on:click="seen = false">Annuler</button>
            <p>{{name}}</p>
        </div>
    </form>
</div>
</template>
<script>

export default{
    data(){
        return{
            seen: false,
            name:"",
            end:"",
            start:"",
            dependencies:"",
            progress:""
        }
    },
    methods:{
        submitTask(){
            const task = {
                id: this.name,
                name: this.name,
                start: this.start,
                end:  this.end,
                dependencies: this.dependencies,
                progress: this.progress,
                _start:""
            }
            this.$emit('newTask',task)
           console.log(task);
        }
        },
    }
</script>
<style>

#addTask{
    display: flex;
    justify-content: center;
}
#form{
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 200px;
    margin-left: 100px;
    padding:5px
}
#cancel, #send{
    background-color: rgb(199, 23, 23);
    padding: 5px;
    margin: 8px;
    width: 60px;
    font-style: oblique;
}
#send{
    background-color: green;
}
</style>
