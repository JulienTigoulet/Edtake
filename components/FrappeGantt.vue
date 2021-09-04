<template>
    <div id="containerGantt">
      <svg id="gantt"></svg>
    </div>
</template>
<script lang="ts">
import Gantt from 'frappe-gantt'
export default({
props: {
    tasks:{
        type:Array,
        required: true
    }
},
mounted() {
    this.NewGanttChart()
  },
  methods:{
      NewGanttChart () {
        this.gantt = new Gantt("#gantt", this.tasks,{
        header_height: 50,
      })
    },
  },  
})
</script>
<style>
#containerGantt{
 margin-right: 20px;
}
</style>
