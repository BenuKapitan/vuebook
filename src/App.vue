<script setup lang="ts">
import { ref } from 'vue';
import Booktable from './components/TableView.vue';
import Bookcard from './components/CardView.vue';
import books from "./bookdata"

const isTableView = ref(false)
</script>

<template>
  <button @click="isTableView = !isTableView">
    {{ isTableView ? "Switch to card view" : "Switch to table view" }}
  </button>
  <Booktable v-if="isTableView" :books="books"/>
  <Bookcard v-else :books="books"/>
</template>

<style scoped>
  button{
    background-color: blue;
    border: none;
    border-radius: 5px;
    min-height: fit-content;
    max-height: 5vh;
    padding: 10px;
    align-self: center;
    justify-self: center;
    position: absolute;
    top: 5%;
    left: 5%;
  }
</style>
