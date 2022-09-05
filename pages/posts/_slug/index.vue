<template>
  <div>
    <PostDetail :post='post' :comments='commentsData' />
  </div>
</template>

<script>
import PostDetail from '~/components/PostDetail.vue'
export default {
  components: {
    PostDetail
  },
  
  async asyncData({ $axios, route }) {
    const slug = route.params.slug
    const postsData = await $axios.$get('/posts')
    const commentsData = await $axios.$get('/comments')
    
    const post = postsData.filter((post)=>{
      return post.slug == slug
    })[0]

    return {
      post,
      commentsData
    }
  },
}
</script>

<style>
</style>