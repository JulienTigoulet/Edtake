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
    <FrappeGantt
    :tasks="tasks"/>
  </div>
</template>

<script>
export default {
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
