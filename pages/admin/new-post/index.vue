<template>
  <div class="admin-new-post">
    <section class="new-post-form">
      <AdminPostForm></AdminPostForm>
    </section>
  </div>
</template>
<script>
import AdminPostForm from "@/components/Admin/AdminPostForm";

export default {
  layout: "admin",
  data() {
    return {
      editPost: {
        author: "",
        title: "",
        thumbnailLink: "",
        content: ""
      }
    };
  },
  methods: {
    onSave() {
      console.log(this.editPost);
    },
    onCancel() {
      this.$router.push("/admin");
    }
  },
  components: {
    AdminPostForm
  }
};
</script>
