<template>
<h1>CREATE ARTICLE</h1>
  <div class="container">
    <input v-model="title" type="text" placeholder="Article Title here..">
    <textarea v-model="content" type="text" placeholder="Article Content here.."></textarea>
    <button @click="addArticle()">Post</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "",
      content: "",
      created: "",
      votes: 0
    }
  },
  props: ['articles'],
  emits: {
  },
  methods: {
    addArticle() {
      this.articles.push({
        title: this.title, 
        content: this.content, 
        votes: this.votes, 
        created: new Date().toString()
      })
    }
  },

}
</script>
<style scoped>
.container{ 
  display: flex;
  flex-direction: column;
  width: 300px;

}
</style>