<script setup>
import { ref } from "vue";

var alumno = ref({
  Nombre: "",
  Curso: "",
  Materia: "",
  Nota: "",
  Estado: "",
});

var alumnos = ref([]);

function enviar() {
  alumnos.value.push({
    Nombre: alumno.value.Nombre,
    Curso: alumno.value.Curso,
    Materia: alumno.value.Materia,
    Nota: alumno.value.Nota,
    Estado: alumno.value.Estado,
  });
  (alumno.value.Nombre = ""),
    (alumno.value.Curso = ""),
    (alumno.value.Materia = ""),
    (alumno.value.Nota = ""),
    (alumno.value.Estado = "");
}
</script>

<template>
  <h1>Formulario Alumnos</h1>
  <br />
  <form action="">
    <label for="">Insertar nombre:</label> <br />
    <input type="text" v-model="Nombre" /> <br />
    <label for="">Curso</label> <br />
    <input type="text" v-model="Curso" /> <br />
    <label for="">Materia </label> <br />
    <input type="text" v-model="Materia" /> <br />
    <label for="">Nota </label> <br />
    <input type="text" v-model="Nota" /> <br />
    <label for="">Estado </label> <br />
    <input type="text" v-model="Estado" /> <br />

    <input type="button" @click="enviar()" value="enviar" />
  </form>

  <h1>Listado de Alumnos</h1>
  <table>
    <tr>
      <th>Nombre</th>
      <br />
      <th>Curso</th>
      <br />
      <th>Materia</th>
      <br />
      <th>Nota</th>
      <br />
      <th>Estado</th>
      <br />
    </tr>
    <tr v-for="enviar in alumnos" :key="enviar">
      <th>{{ enviar.Nombre }}</th>
      <br />
      <th>{{ enviar.Curso }}</th>
      <br />
      <th>{{ enviar.Materia }}</th>
      <br />
      <th>{{ enviar.Nota }}</th>
      <br />
      <th>{{ enviar.Estado }}</th>
      <br />
    </tr>
  </table>
</template>

<style scoped></style>
