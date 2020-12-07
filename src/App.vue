<template>
  <div id="app">

    <Header theTitle="Popular TV Shows"/>
    <TaskList theTitle = "My Tasks" :taskList="tasks"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import TaskList from './components/Card.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header, 
    TaskList
  },
  data()
  {
    return {
      tasks: [
        //{id:1, title: "Learns HTML & CSS", completed: false},
        //{id:2, title: "Learn Javascript", completed: false},
        //{id:3, title: "Learn a JS Framework", completed: false}
      ]
    }
  },
  mounted()
    {

        axios.get('https://api.themoviedb.org/3/tv/popular?api_key=571018b708e3c5a431f7569452cb4421&language=en-US&page=1')
        
        //https://api.themoviedb.org/3/movie/now_playing?api_key=571018b708e3c5a431f7569452cb4421&language=en-US&page=1')


        .then( (response)=> {
            this.tasks = response.data.results.slice(0,4);
        })

    }
}
</script>

<style>
 * {
   margin: 0;
   padding: 0;
 }
</style>
