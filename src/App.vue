<script setup>
import { ref } from 'vue';

// Variabel reaktif dengan ref
const title = ref('Belajar Vue 3!');
const username = ref('Jane Doe');
const userInput = ref('');
const clickCount = ref(0);
const imageSource = ref('https://via.placeholder.com/200');
const showText = ref(true);

// Event handler
const addClick = () => {
  clickCount.value++;
};

const toggleText = () => {
  showText.value = !showText.value;
};
</script>

<template>
  <div>
    <!-- Text Interpolation -->
    <h1>{{ title }}</h1>
    <h2>Welcome, {{ username }}!</h2>

    <!-- Form Binding -->
    <input v-model="userInput" placeholder="Masukkan teks..." />
    <p>Input: {{ userInput }}</p>

    <!-- Event Listener -->
    <button @click="addClick">Tambah Klik</button>
    <p>Total Klik: {{ clickCount }}</p>

    <!-- Attribute Binding -->
    <img :src="imageSource" alt="Gambar Contoh" />

    <!-- Conditional Rendering -->
    <button @click="toggleText">Tampilkan/Sembunyikan</button>
    <p v-if="showText">Teks ini bisa disembunyikan dengan tombol.</p>
  </div>
</template>