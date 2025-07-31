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
  <form class="formulario" action="">
    <label for="">Nombre:</label> <br />
    <input type="text" v-model="alumno.Nombre" /> <br />
    <label for="">Curso</label> <br />
    <input type="text" v-model="alumno.Curso" /> <br />
    <label for="">Materia </label> <br />
    <input type="text" v-model="alumno.Materia" /> <br />
    <label for="">Nota </label> <br />
    <input type="text" v-model="alumno.Nota" /> <br />
    <label for="">Estado </label> <br />
    <select v-model="alumno.Estado">
      <option value="Aprobado">Aprobado</option>
      <option value="Reprobado">Reprobado</option>
    </select>
    <br />
    <button type="button" @click="enviar()" value="enviar">Enviar</button>
  </form>
  <br />

  <h1>Listado de Alumnos</h1>
  <br />
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

<style scoped>
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f5f5f5;
  margin: 0;
  padding: 0;
}

h1 {
  text-align: center;
  color: #2c3e50;
  font-size: 50px;
  margin: 20px 0;
}

.formulario {
  max-width: 500px;
  background-color: #fff;
  margin: 0 auto;
  padding: 20px 25px;
  border-radius: 12px;
  box-shadow: 0 4px 14px rgba(0, 0, 0, 0.08);
  display: flex;
  flex-direction: column;
  gap: 12px;
}

label {
  font-weight: 600;
  margin-bottom: 2px;
  color: #333;
  font-size: 20px;
}

input,
select {
  width: 100%;
  padding: 6px 10px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 14px;
}

input:focus,
select:focus {
  outline: none;
  border-color: #4caf50;
}

button {
  padding: 8px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 6px;
  font-weight: bold;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.2s;
  margin-top: 8px;
}

button:hover {
  background-color: #388e3c;
}

/* Tabla */
table {
  width: 90%;
  margin: 30px auto 0;
  border-collapse: collapse;
  font-family: Arial, sans-serif;
  font-size: 14px;
}

th,
td {
  border: 1px solid #ccc;
  padding: 10px;
  text-align: left;
}

th {
  background-color: #eee;
  color: black;
}
</style>
