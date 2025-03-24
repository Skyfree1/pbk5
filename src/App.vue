<script setup>
import { ref } from 'vue';

const message = ref('Hello, gays');
const count = ref(0);
const isVisible = ref(true);
const inputText = ref('');
const imageUrl = ref('https://vuejs.org/images/logo.png');

const increment = () => {
  count.value++;
};

const toggleVisibility = () => {
  isVisible.value = !isVisible.value;
};
</script>

<template>
  <div>
    <h1>{{ message }}</h1>

    <input v-model="inputText" placeholder="Ketik sesuatu..." />
    <p>Hasil input: {{ inputText }}</p>

    <button @click="increment">Klik disini! (Count: {{ count }})</button>

    <img :src="imageUrl" alt="Vue Logo" width="100" />

    <p v-if="isVisible">Teks ini terlihat!</p>
    <p v-else>Teks ini tersembunyi!</p>

    <button @click="toggleVisibility">Tampilkan/Sembunyikan</button>
  </div>
</template>

<style scoped>
button {
  margin-top: 10px;
  padding: 5px 10px;
  background-color: #42b883;
  border: none;
  color: white;
  cursor: pointer;
  border-radius: 5px;
}
button:hover {
  background-color: #35495e;
}
</style>
