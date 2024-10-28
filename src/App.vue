<template>
  <div id="app">
    <h1>Welcome to My Vue.js Blog</h1>
    <div class="blog-list">
      <BlogPost
        v-for="post in blogPosts"
        :key="post.id"
        :title="post.title"
        :content="post.content"
        :likes="post.likes"
        @likePost="handleLikePost(post.id)"
      />
    </div>
  </div>
</template>

<script>
import BlogPost from './components/BlogPost.vue'

export default {
  props: {},
  name: 'App',
  components: {
    BlogPost
  },
  data() {
    return {
      blogPosts: [
        { id: 1, title: 'Vue.js Basics', content: 'Learning the fundamentals of Vue.js', likes: 0 },
        {
          id: 2,
          title: 'Understanding Components',
          content: 'How to build components in Vue.js',
          likes: 0
        },
        {
          id: 3,
          title: 'Vue.js Lifecycle',
          content: 'An overview of Vue.js lifecycle methods',
          likes: 0
        }
      ]
    }
  },
  methods: {
    handleLikePost(postId) {
      const post = this.blogPosts.find((p) => p.id === postId)
      if (post) {
        post.likes += 1
      }
    }
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  margin: 40px auto;
  max-width: 600px;
}

.blog-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>


