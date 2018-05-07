<template>
  <div class="single-post-page">
      <section class="post">
          <h1 class="post-title"> {{loadedPosts.title}} </h1>
          <div class="post-details">
              <div class="post-detail">Last updated on {{loadedPosts.updatedDate}} </div>
              <div class="post-detail">Written by {{loadedPosts.author}}</div>
          </div>
          <p>Content of the post</p>
          <section class="post-feedback">
              <p class="post-content"> {{loadedPosts.content}} </p>
          </section>
      </section>
  </div>
</template>
<script>
export default {
  data() {
    return {
      loadedPosts: []
    };
  },
  asyncData(context, callback) {
    setTimeout(() => {
      callback(null, {
        loadedPosts: {
          title: `First post (ID: ${context.params.id})`,
          author: "Nael",
          updatedDate: new Date(),
          content: "Some dummy text which is definitely not the preview text",
          previewText: "This is our first post !",
          thumbnail:
            "https://i1.wp.com/www.insider-trends.com/wp-content/uploads/2016/11/Top-50-retail-tech-startups-in-world-01.jpeg"
        }
      });
    }, 1500);
  }
};
</script>
<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>
