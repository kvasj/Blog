<template>
  <div class="col-md-6">
    <div class="row g-0 border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative">
      <div class="col p-4 d-flex flex-column position-static">
        <h3 class="mb-0">{{ title }}</h3>
        <div class="mb-1 text-muted">{{ formatedDate }}</div>
        <p class="card-text mb-auto">{{ cutedContent }}</p>
        <nuxt-link :to="`/posts/${slug}`" v-if="slug">Continue reading</nuxt-link>
      </div>
      <div class="col-auto d-none d-lg-block">
        <img :src="image" alt="" width="200" height="250" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['createdAt', 'title', 'content', 'slug', 'image'],

  computed: {
    formatedDate() {
      return new Date(this.createdAt).toDateString()
    },

    cutedContent() {
      return this.content.substring(0, 50) + "...";
    },
  },
}
</script>