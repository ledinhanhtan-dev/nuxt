<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news!</h1>
    </section>
    <section class="featured-posts">
      <nuxt-link
        :to="toPost"
        class="post-preview"
        v-for="post in posts"
        :key="post.id"
      >
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
    </section>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',

  data() {
    return {
      posts: [
        {
          id: 'p1',
          title: 'Post Title 1',
          preview: 'Preview Text 1',
          image:
            'https://mlmuuous6dwe.i.optimole.com/DfwWcdQ-JK5kWYU6/w:auto/h:auto/q:auto/https://technation.io/wp-content/uploads/2017/11/91F5041A-B5D4-4648-AA55-C39A0DBBAAC3.jpeg',
        },
        {
          id: 'p2',
          title: 'Post Title 2',
          preview: 'Preview Text 2',
          image:
            'https://www.intelligenthq.com/wp-content/uploads/2020/09/How-Tech-is-Changing-the-Way-we-Work-600x375.jpg',
        },
      ],
    }
  },

  computed: {
    toPost() {
      return `/posts/2`
    },
  },
}
</script>

<style lang="scss" scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  box-sizing: border-box;
  background-position: center;
  background-size: cover;
}

.intro h1 {
  position: absolute;
  top: 10%;
  left: 5%;
  width: 90%;
  font-size: 1.5rem;
  color: black;
  background-color: rgb(211, 211, 211);
  padding: 10px;
  border-radius: 10px;
  box-shadow: 3px 3px 3px black;
  box-sizing: border-box;
  border: 1px solid black;
}

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}

.featured-posts {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

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
