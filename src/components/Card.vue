<template>
    <div class="center">
        <div v-for="task in taskList" :key="task.id" class="container">
            <img v-bind:src="'https://image.tmdb.org/t/p/w300//' + task.poster_path">
            <h1>{{task.name}}</h1>
            <p>{{task.overview}}</p>
        </div>
        
        <Task :aTask="task" /> 
    </div>
</template>

<script>
import Task from "./Task.vue";
export default {
    name:"TaskList",
    props:['theTitle', 'taskList'],
    components: {
        Task
    }
}
</script>

<style scoped>

.center {
    display: flex;
    justify-content: center;
    padding: 250px;
}

.container {
    max-width: 25%;
    background-color: wheat;
    padding: 25px;
    border-radius: 25px;
    box-shadow: 0 0 100px 20px;
}

img {
    display: block;
    margin-left: auto;
    margin-right: auto;
}

h1 {
    text-align: center;
}

</style>