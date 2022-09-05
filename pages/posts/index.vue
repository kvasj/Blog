<template>
  <div class="post-list">
    <PostList :posts='postsData' />
  </div>

</template>

<script>
import PostList from '../../components/PostList.vue'
export default {
  components: {
    PostList,
  },

  async asyncData({ $axios }) {
    const postsData = await $axios.$get('/posts')
    return {
      postsData,
    }
  },
}
</script>