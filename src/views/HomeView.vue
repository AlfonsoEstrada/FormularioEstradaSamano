<template>
  <div class="formulario">
    <H1>Formulario 21393135 </H1>
    <h3>Llena los siguientes campos</h3>
    <form @submit.prevent="submitForm">
      <div class="micro">
        <label class="name" for="nombre">Nombre:</label>
        <input type="text" id="nombre" v-model="nombre" @input="validateNombre" /><br />

        <label class="lastname" for="apellido">Apellido:</label>
        <input type="text" id="apellido" v-model="apellido" @input="validateApellido" /><br />

        <label for="edad" class="edad">Edad:</label>
        <input type="number" id="edad" v-model="edad" @input="validaEdad" /><br />

        <label for="genero" class="genero">Género:</label>
        <select id="genero" v-model="generoSeleccionado">
          <option value="masculino">Masculino</option>
          <option value="femenino">Femenino</option>
          <option value="otro">Otro</option>
        </select>
        <input
          type="text"
          v-if="generoSeleccionado === 'otro'"
          v-model="otroGenero"
          placeholder="Especificar otro género"
        /><br />
        <button type="submit" :disabled="!formValid">Enviar</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nombre: '',
      apellido: '',
      edad: 0,
      generoSeleccionado: 'masculino',
      otroGenero: '',
      formValid: false
    }
  },
  methods: {
    validateNombre() {
      this.formValid = this.nombre.length >= 5 && this.nombre.length <= 18
    },
    validateApellido() {
      this.formValid = this.apellido !== this.nombre
    },
    validaEdad() {
      this.formValid = this.edad >= 18
    },
    submitForm() {
      console.log('Formulario enviado:', {
        nombre: this.nombre,
        apellido: this.apellido,
        edad: this.edad,
        genero: this.genero
      })
    }
  }
}
</script>

<style>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  margin-top: 20px;
  background-color: #06593d;
  padding: 1rem;
  border-radius: 1rem;
}

.micro {
  background-color: #065959;
  padding: 2rem;
}

.edad {
  text-align: start;
  padding-right: 1.4rem;
}

.genero {
  text-align: start;
  padding-right: 1.4rem;
}

label {
  margin-right: 1rem;
}

input,
select {
  margin-bottom: 10px;
  padding: 6px;
}

input {
  border: none;
  border-radius: 0.3rem;
}

button {
  padding: 10px;
  background-color: #4caf50;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:disabled {
  background-color: #aaa;
  cursor: not-allowed;
}

input[type='number']::-webkit-inner-spin-button,
input[type='number']::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
