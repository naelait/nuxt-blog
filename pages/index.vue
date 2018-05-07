<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news !</h1>
    </section>
    <PostList :posts="loadedPosts"></PostList>
  </div>
</template>
<script>
import PostList from "@/components/Posts/PostList";

export default {
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
  components: {
    PostList
  }
};
</script>
<style scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  background-image: url("~assets/images/background.jpg");
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
</style>
