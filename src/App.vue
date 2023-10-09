<script setup>
import { reactive } from 'vue';
import Progress from './components/Progress.vue'

let newCourse = {done:false};

let courses = reactive([
  {
    title: 'Javascript',
    done: true
  },  
  {
    title: 'React',
    done: false
  },  
  {
    title: 'Vue',
    done: false
  },
])

function addCourse () {
  courses.push(newCourse);
  newCourse = {done:false}
}


</script>
<template>
  <div>
      <h1>Lista de Cursos</h1>
      <h2 v-for="(course, index) in courses" :key="index">
          {{ course.title }}
      </h2>

      <br/>
      <input v-model="newCourse.title" type="text">
      <button @click="addCourse">Adicionar</button>
    </div>
    <Progress :courses="courses"/>
  </template>  

<style scoped>
</style>
