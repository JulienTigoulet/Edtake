<template>
    <div class="containerTask">
        <table rules="columns">
            <tbody>
                <tr>
                    <td>Tâche</td>
                    <td>{{task}}</td>
                </tr>
                <tr>
                    <td>Début</td>
                    <td>{{start}}</td>
                </tr>
                <tr>
                    <td>Fin</td>
                    <td>{{end}}</td>
                </tr>
                <tr>
                    <td>Progression</td>
                    <td>{{progress}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
export default {
    props:{
        task: String,
        end: Date,
        start: Date,
        progress: Number,
    },
}
</script>
<style>
table,td{
    border: 1px solid #333;
    overflow: auto;
}
.containerTask{
    width:500px;
    font-size: smaller;
}
</style>
