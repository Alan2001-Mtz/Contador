<template>
  <Navbar /> <!-- Incluye el componente Navbar -->
  <div class="container">
    <div class="row mt-2">
      <div class="col-3">
        <h4
          :class="{
            'text-primary': counter > 0,
            'text-danger': counter < 0,
            'text-warning': counter === 0,
          }"
        >
          Contador: {{ counter }}
        </h4>
        <button class="btn btn-increment" @click="handledIncrement">+ 1</button>
        <button class="btn btn-reset m-2" @click="resetCounter">Reset</button>
        <button class="btn btn-decrement m-2" @click="handledDecrement">- 1</button>
        <button
          class="btn btn-success m-2"
          @click="addToStore"
          :disabled="almacenador.includes(counter)"
        >
          Agregar Numero
        </button>
      </div>
      <div class="col">
        <h5>Almacenar los numeros</h5>
        <ul class="store-list">
          <li v-for="(num, index) in almacenador" :key="index">{{ num }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Navbar from './components/Navbar.vue'; // Asegúrate de que la ruta sea correcta

const counter = ref(0);
const almacenador = ref([]);

const handledIncrement = () => {
  counter.value += 1;
};

const handledDecrement = () => {
  counter.value -= 1;
};

const resetCounter = () => {
  counter.value = 0;
};

const addToStore = () => {
  if (!almacenador.value.includes(counter.value)) {
    almacenador.value.push(counter.value);
  }
};
</script>
