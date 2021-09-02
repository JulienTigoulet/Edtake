<template>
  <div class="container">
    <div id="containerTasks">
      <div id="title">
        <h3>Le tableau des tâches</h3>
      </div>
          <Task
          v-for="task in tasks"
          :key="task.id"
          :task="task.name"
          :start="task._start"
          :progress="task.progress"
          :end="task._end">
          </Task> 
    </div>
    <!-- <form>
      <label for="name">Nom de la tâche</label>
      <input type="name" ref="name">
      <label for="start"> Début de la tâche</label>
      <input type="date" ref="start">
      <label for="end">Fin de la tâche</label>
      <input type="date" ref="end">
      <label for="depencies">Dépendant d'une tâche</label>
      <input type="texte" ref="depencies" placeholder="utiliser le nom d'une tâche déjà existante">
        <button @click.prevent="addTask()">Ajout d'une tâche</button>
    </form> -->
    <FrappeGantt
    :tasks="tasks"/>
  </div>
</template>

<script>
export default {
  // methods:{
  //   addTask(){  
  //     this.tasks.push ({
  //       name : this.$refs.name.value,
  //       start : this.$refs.name.value,
  //       end : this.$refs.name.value,
  //       id : this.$refs.name.value,
  //       depencies : this.$refs.name.value,
  //       _start:""
  //     })
  //   }
  // },
  data() { 
    return {
      tasks: [
      {
        id: 'task 1',
        name: 'Just Do It',
        start: '2021-8-23',
        end: '2021-8-28',
        progress: 10,
        dependencies: '',
        _start: "",
      },
      {
        id: 'task 2',
        name: 'Do It ',
        start:'2021-8-24',
        end: '2021-8-25',
        dependencies:'task 1',
        progress:0,
        _start: "",
      },
      {
        id: 'task 3',
        name: 'Well done',
        start:'2021-9-1',
        end: '2021-9-2',
        dependencies:'',
        progress:0,
        _start: "",
      }
    ],
  }
  },
}
</script>
<style>
.container{
  display: flex;
  flex-direction: row-reverse;
}
#containerGantt{
  width: 500px;
}
#title{
  display: flex;
  justify-content: center;
}
</style>
