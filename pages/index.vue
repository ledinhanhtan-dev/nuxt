<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news!</h1>
    </section>
    <section class="featured-posts">
      <PostPreview v-for="post in posts" :key="post.id" :post="post" />
    </section>
  </div>
</template>

<script>
import PostPreview from '@/components/posts/PostPreview.vue'
export default {
  name: 'IndexPage',
  components: { PostPreview },
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
  background-image: url('~assets/images/main-page-background.jpg');
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
</style>
