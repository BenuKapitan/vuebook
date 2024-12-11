<script setup lang="ts">
import { type Book } from '../models/BookModel';

defineProps<{ books: Book[] }>();
</script>

<template>
  <div class="book-container">
    <div v-for="book in books" :key="book.title" class="book-card">
      <img :src="book.img_url" :alt="book.title" class="book-image">
      <h2 class="book-title">{{ book.title }}</h2>
      <p class="book-author">By: {{ book.author }}</p>
      <p class="book-description">{{ book.description }}</p>
    </div>
  </div>
</template>

<style scoped>
.book-container {
  height: 100%;
  width: 100rem;
  display: flex;
  flex-direction: row;
  justify-content:flex-start;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
  padding: 20px;
}

.book-card {
  background: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 16px;
  text-align: center;
  transition: transform 0.2s, box-shadow 0.2s;
  max-width: 300px;
}

.book-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
}

.book-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
  margin-bottom: 12px;
}

.book-title {
  font-size: 1.5em;
  font-weight: bold;
  margin: 10px 0;
  color: black;
}

.book-author {
  font-size: 1.1em;
  color: black;
  margin-bottom: 8px;
}

.book-description {
  font-size: 0.9em;
  color: black;
}
</style>
