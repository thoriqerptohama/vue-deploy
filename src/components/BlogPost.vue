<template>
  <div class="blog-post">
    <h2>{{ title }}</h2>
    <p>{{ content }}</p>
    <button @click="likePost">Like</button>
    <p>Likes: {{ likes }}</p>
  </div>
</template>

<script>
export default {
  name: 'BlogPost',
  props: {
    title: String,
    content: String,
    likes: Number
  },
  methods: {
    likePost() {
      this.$emit('likePost')
    }
  }
}
</script>

<style scoped>
.blog-post {
  border: 1px solid #ddd;
  padding: 20px;
  border-radius: 8px;
  text-align: left;
}

button {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 8px 12px;
  cursor: pointer;
  border-radius: 4px;
}

button:hover {
  background-color: #358a6b;
}
</style>


