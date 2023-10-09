<script setup>
import { ref ,reactive } from 'vue';

// ref para primitivos: valores ficam armazenados dentro do value
let count = ref(0);

// reactive para objetos

let newCourse = {};

let courses = reactive([
  {
    title: 'Javascript'
  },  
  {
    title: 'React'
  },  
  {
    title: 'Vue'
  },
])

function addCourse () {
  courses.push(newCourse);
  newCourse = {}
}

function increment() {
  count.value++;
}


</script>
<template>
  <div>
      <h1>{{ count }}</h1>
      <button @click="increment">Incrementar</button>

      <h1>Lista de Cursos</h1>
      <h2 v-for="(course, index) in courses" :key="index">
          {{ course.title }}
      </h2>

      <br/>
      <input v-model="newCourse.title" type="text">
      <button @click="addCourse">Adicionar</button>
  </div>
</template>

<style scoped>
</style>
