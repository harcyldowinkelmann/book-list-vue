<script setup>
  import { reactive } from 'vue';
  import Progress from './components/Progress.vue';

  // reactive usado, convencionalmente, para objetos reativos e dinâmicos
  let courses = reactive([
    {
      title: "JavaScript",
      description: "Curso básico de JavaScript",
      done: true
    },
    {
      title: "React",
      description: "Curso básico de React",
      done: false
    },
    {
      title: "Vue",
      description: "Curso básico de Vue",
      done: true
    }
  ]);

  let newCourse = {done:false};

  function addCourse() {
    courses.push(newCourse);
    newCourse = {done:false};
  }

</script>

<template>
  <div>
    <h1>Lista de Cursos</h1>
    <ul>
      <li v-for="course in courses" :key="course.title">
        {{ course.title }}
        <ul>
          <li>{{ course.description }}</li>
        </ul>
      </li>
    </ul>

    <br />

    <p>Adicionar curso:</p>
    <input v-model="newCourse.title" type="text" placeholder="Nome do curso..."> <br />
    <input v-model="newCourse.description" type="text" placeholder="Descrição do curso..."> <br />
    <button @click="addCourse()">Adicionar</button>

    <Progress :courses="courses" />

  </div>
</template>

<style scoped>

</style>
