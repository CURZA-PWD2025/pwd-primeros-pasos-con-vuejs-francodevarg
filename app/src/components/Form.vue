<template>
    <form @submit.prevent="submitForm">
      <h1>Crear Usuario</h1>
      <label for="username">Nombre de Usuario:</label>
      <input v-model="user.username" type="text" id="username" required />

      <label for="email">Email:</label>
      <input v-model="user.email" type="email" id="email" required />

      <label for="password">Contraseña:</label>
      <input v-model="user.password" type="password" id="password" required />

      <label for="dateOfBirth">Fecha de Nacimiento:</label>
      <input v-model="user.dateOfBirth" type="date" id="dateOfBirth" required />

      <button type="submit">Crear Usuario</button>
    </form>
</template>

<script setup lang="ts">
import { ref } from "vue";

interface Usuario {
  username: string;
  email: string;
  password: string;
  dateOfBirth: string;
}

const user = ref<Usuario>({
  username: "",
  email: "",
  password: "",
  dateOfBirth: "",
});

const submitForm = () => {
  alert(`Usuario creado: ${JSON.stringify(user.value)}`);
  cleanForm();
};

const cleanForm = () => {
  user.value = {
    username: "",
    email: "",
    password: "",
    dateOfBirth: "",
  };
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  max-width: 400px;
  margin: 0 auto;
}

label {
  margin-top: 10px;
}

input {
  margin-bottom: 15px;
  padding: 8px;
  font-size: 16px;
}

button {
  background-color: #4CAF50;
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
</style>
