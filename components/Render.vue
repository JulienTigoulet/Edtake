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
        id: 'Just Do It',
        name: 'Just Do It',
        start: '2021-9-1',
        end: '2021-9-2',
        progress: 10,
        dependencies: '',
        _start: '',
      },
      {
        id: 'Do It',
        name: 'Do It ',
        start:'2021-9-2',
        end: '2021-9-4',
        dependencies:'Just Do It',
        progress:0,
        _start: "",
      },
      {
        id: 'Well done',
        name: 'Well done',
        start:'2021-9-5',
        end: '2021-9-6',
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
  width: 800px;
}
#title{
  display: flex;
  justify-content: center;
}

#containerTasks{
  border-top: 0.1px solid rgb(197, 169, 169);
}
</style>
