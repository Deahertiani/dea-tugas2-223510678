<template>
  <div>
    <input type="text" placeholder="Masukkan sesuatu" v-model="inputText" :class="inputClass" :style="{ borderColor: inputBorderColor }">
    <p>{{ inputText }}</p>

    <p v-bind:class="titleclass">
    Perkenalkan nama saya Dea Hertiani 
    </p>
    <h3 v-bind:class="titleclass">
    Saya biasa di panggil Dea </h3>
    <h3 v-bind:class="titleclass">
    Saya berasal dari kelas 4E </h3>

    <h1>Event Listener</h1>
    <button @click="changeColor">Ubah Warna</button>
    <div :style="{ backgroundColor: bgColor, padding: '10px' }">{{ message }}</div>

   
  </div>
</template>

<script setup>
import { ref } from 'vue';

const titleclass = ref("class");
const inputText = ref('');
const inputClass = 'input-style';
const inputBorderColor = 'lightblue';

const message = ref('Klik tombol di atas untuk mengubah warna!');
const bgColor = ref('black');

const changeColor = () => {
  bgColor.value = '#' + Math.floor(Math.random() * 16777215).toString(16);
};
</script>

<style scoped>
.class {
  font-size: 25px;
  color: rgb(215, 114, 148);
}

.input-style {
  width: 200px;
  padding: 10px;
  border: 2px solid;
  border-radius: 5px;
  font-size: 16px;
}
</style>