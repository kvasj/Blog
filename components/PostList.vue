<template>
  <div class="row mb-2">
    <PostPreview
      v-for="post in posts"
      :key="post.id"
      :createdAt="post.createdAt"
      :title="post.title"
      :content="post.content"
      :slug="post.slug"
      :image="post.image"
    />
  </div>
</template>

<script>
import PostPreview from '../components/PostPreview.vue'
export default {
  components: {
    PostPreview,
  },

  props: ['posts']
}
</script>
