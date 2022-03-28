<template>
<h1>ARTICLE DETAIL</h1>
  <div>ARTICLE TITLE: {{this.title}}</div>
  <div>CONTENT: {{this.content}}</div>
  <div>VOTES: {{this.votes}} 
    <button @click="$emit('upvote', index)">UP</button>
    <button @click="$emit('downvote', index)">DOWN</button>
  </div>
  <div>DATE CREATED: {{this.created}}</div>

</template>
<script>
export default {
  props: [ 'title', 'content', 'votes', 'created', 'index'],
  data() {
    return {

    }
  },
  methods: {
  }
}
</script>