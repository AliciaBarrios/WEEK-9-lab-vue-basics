<script setup>
import { ref, onMounted } from "vue";

const mensaje = "Resultado en el footer:";
const suma = ref();
let isVisible = ref(true);
let isActive = ref(true);

onMounted(() => {
  console.log(suma.value);
});

function changeBox() {
  isActive.value = !isActive.value;
  isVisible.value = !isVisible.value;
}
</script>

<template>
  {{ mensaje }}
  <p ref="suma">{{ 2 + 2 }}</p>
  <div class="container" :class="{ blackBackgroundColor: isActive }">
    <h1 v-show="isVisible">Esto del Vue.js mola!</h1>
    <button @click="changeBox" type="button">
      Apretar para cambiar estilos del recuadro
    </button>
  </div>
</template>

<style scoped>
h1 {
  color: white;
  text-align: center;
}
.container {
  display: flex;
  flex-direction: column;
  background-color: rgba(15, 112, 15, 0.719);
  padding: 2.5rem 0;
}
.blackBackgroundColor {
  background-color: black;
}
button {
  padding: 0.5rem;
  background-color: rgba(211, 219, 103, 0.877);
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 30%;
  margin: 1rem auto;
}
</style>
