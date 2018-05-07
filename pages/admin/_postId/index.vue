<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost"></AdminPostForm>
    </section>
  </div>
</template>
<script>
import AdminPostForm from "@/components/Admin/AdminPostForm";

export default {
  layout: "admin",
  data() {
    return {
      loadedPost: {
        author: "Nael",
        title: "My awesome Post",
        thumbnailLink:
          "https://i1.wp.com/www.insider-trends.com/wp-content/uploads/2016/11/Top-50-retail-tech-startups-in-world-01.jpeg",
        content: "Super Amazing, thanks for that !"
      }
    };
  },
  components: {
    AdminPostForm
  }
};
</script>
