<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts"></PostList>
  </div>
</template>
<script>
import PostList from "~/components/Posts/PostList";

export default {
  components: {
    PostList
  },
  asyncData(context, callback) {
    setTimeout(() => {
      callback(null, {
        loadedPosts: [
          {
            id: "1",
            title: "first Post",
            previewText: "This is our first post !",
            thumbnail:
              "https://i1.wp.com/www.insider-trends.com/wp-content/uploads/2016/11/Top-50-retail-tech-startups-in-world-01.jpeg"
          },
          {
            id: "2",
            title: "second Post",
            previewText: "This is our second post !",
            thumbnail:
              "https://i1.wp.com/www.insider-trends.com/wp-content/uploads/2016/11/Top-50-retail-tech-startups-in-world-01.jpeg"
          }
        ]
      });
    }, 1500);
  },
  created() {
    this.$store.dispatch("setPosts", this.loadedPosts);
  }
};
</script>
<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
