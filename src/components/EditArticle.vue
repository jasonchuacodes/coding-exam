<template>
  <h1>EDIT ARTICLE</h1>
  <div>ARTICLE TITLE: {{ this.title }}</div>
  <div>CONTENT: {{ this.content }}</div>
  <input v-model="editedContent" type="text">
  <button @click="$emit('update', index, editedContent)">Update</button>
</template>

<script>
export default {
  props: ['title', 'content', 'index'],
}
</script>