<template>
  <button @click="">CREATE NEW ARTICLE</button>
  <button @click="">EDIT ARTICLE</button>
  <br>
  <create-article 
    :articles="articles"
  />

  <br>

  <article-detail 
    v-for="(article, i) in articles"
    :key="i"
    :title="article.title"
    :content="article.content"
    :votes="article.votes"
    :created="article.created"
    :index="i"
    @upvote="upvote"
    @downvote="downvote"
  />

  <br>

  <edit-article 
    v-for="(article, i) in articles"
    :key="i"
    :title="article.title"
    :content="article.content"
    :votes="article.votes"
    :created="article.created"
    :index="i"
    @update="update"
  />
  
</template>
<script>
import CreateArticle from './CreateArticle.vue'
import ArticleDetail from './ArticleDetail.vue'
import EditArticle from './EditArticle.vue'

export default {
  components: {
    CreateArticle,
    ArticleDetail,
    EditArticle
  },
  data() {
    return {
      articles: [ 
      ],
      isEditing: null,
      articleContent: ""
    }
  },
  methods: {
    upvote(n) {
      this.articles[n].votes += 1
    },
    downvote(n) {
      this.articles[n].votes -= 1
    },
    update(n, editedContent) {
      this.articleContent = editedContent
      this.articles[n].content = this.articleContent
      this.articleContent = ""
    }
  }
}
</script>