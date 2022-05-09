<template>
  <nuxt-link :to="'/posts/' + post.id" class="post-preview">
    <article>
      <div
        class="post-thumbnail"
        :style="{ backgroundImage: 'url(' + post.image + ')' }"
      ></div>
      <div class="post-content">
        <h1>{{ post.title }}</h1>
        <p>{{ post.preview }}</p>
      </div>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  name: 'PostPreview',
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style coped>
.post-preview {
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #ccc;
  background-color: white;
  width: 90%;
}

a {
  text-decoration: none;
  color: black;
}

@media (min-width: 850px) {
  .post-preview {
    width: 400px;
    margin: 10px;
  }
}

.post-thumbnail {
  z-index: 1;
  width: 100%;
  height: 200px;
  background-position: center;
  background-size: cover;
  position: relative;
}

.post-content {
  z-index: 2;
  padding: 10px;
  text-align: center;
  position: relative;
  background-color: white;
}

a:hover .post-content,
a:active .post-content {
  background-color: #ccc;
}
</style>
