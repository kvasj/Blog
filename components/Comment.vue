<template>
  <div class="comment-wrapper">
    <div class="profile">
      <img :src="avatar" alt="" width="80" height="80" />
      <div class="info">
        <h5>{{ name }}</h5>
        <span class="text-muted">{{ createdAt }}</span>
      </div>
    </div>
    <div class="comment">
      <p>{{ comment }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['avatar', 'name', 'createdAt', 'comment'],
}
</script>

<style scoped>
.comment-wrapper {
  display: flex;
  border-bottom: 1px solid #e5e5e5;
  margin-bottom: 20px;
  padding: 5px;
}

.comment-wrapper .comment p{
  margin: 0px;
}

.profile {
  display: flex;
  margin-bottom: 10px;
  width: 250px;
  border-right: 1px solid #e5e5e5;
  margin-right: 20px;
}

.info{
  padding: 10px;
  margin-left: 5px;
  display: flex;
  flex-flow: column;
  justify-content: space-around;
}

.info span{
  font-size: small;
}
</style>