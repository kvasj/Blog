<template>
  <div class="post-wrapper">
    <div class="post-content">
      <h2 class="blog-post-title mb-1">{{ title }}</h2>
      <p class="blog-post-meta">{{ createdAt }}</p>
      <p>{{ content }}</p>
    </div>

    <img :src="image" alt="" width="492" height="370" />
  </div>
</template>

<script>
export default {
  props: ['createdAt', 'title', 'content', 'image'],
}
</script>

<style scoped>
.post-wrapper {
  display: flex;
  margin-bottom: 20px;
}
.post-content {
  margin-right: 40px;
}
.post-content p{
  text-align: justify;
}
</style>