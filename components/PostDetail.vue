<template>
  <div>
    <article class="blog-post">
      <Post
        :title="post.title"
        :createdAt="formatedDate(post.createdAt)"
        :content="post.content"
        :image="post.image"
      />

      <h3>Comments:</h3>
      <Comment
        v-for="comment in comments"
        :key="comment.id"
        :avatar="comment.avatar"
        :name="comment.name"
        :createdAt="formatedDate(comment.createdAt)"
        :comment="comment.comment"
      />
    </article>
  </div>
</template>

<script>
import Post from './Post.vue'
import Comment from './Comment.vue'
export default {
  components: {
    Post,
    Comment,
  },
  props: ['post', 'comments'],

  methods: {
    formatedDate(date) {
      return new Date(date).toDateString()
    },
  },
}
</script>