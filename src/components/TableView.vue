<script setup lang="ts">
import { type Book } from '../models/BookModel';

defineProps<{ books: Book[] }>();
</script>

<template>
  <table class="book-table">
    <thead>
      <tr>
        <th>Author</th>
        <th>Title</th>
        <th>Description</th>
        <th>Image</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="book in books" :key="book.title">
        <td>{{ book.author }}</td>
        <td>{{ book.title }}</td>
        <td>{{ book.description }}</td>
        <td>
          <img :src="book.img_url" :alt="book.title" class="book-image">
        </td>
      </tr>
    </tbody>
  </table>
</template>

<style scoped>
.book-table {
  width: 100rem;
  height: 100rem;
  border-collapse: collapse;
  margin: 20px 0;
  font-size: 16px;
  text-align: left;
  background-color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.book-table th,
.book-table td {
  border: 1px solid #ccc;
  padding: 12px 15px;
  color: black;
}


.book-table tr:nth-child(even) {
  background-color: #f9f9f9;
}
.book-table th {
  background-color: #f7f7f7;
  font-weight: 600;
  color: #333;
}

.book-image {
  max-width: 100px;
  height: auto;
  display: block;
  border-radius: 5px;
}

.book-table tr:hover {
  background-color: #f1f1f1;
}
</style>
