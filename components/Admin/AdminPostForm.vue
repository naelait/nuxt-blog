<template>
  <form @submit.prevent="onSave">
        <AppControlInput v-model="editPost.author">Author Name</AppControlInput>

        <AppControlInput v-model="editPost.title">Title</AppControlInput>

        <AppControlInput v-model="editPost.thumbnailLink">Thumbnail Link</AppControlInput>

        <AppControlInput control-type="textarea" v-model="editPost.content">Content</AppControlInput>

        <AppButton type="submit">Save</AppButton>

        <AppButton type="button" style="margin-left: 10px" btn-style="cancel" @click="onCancel">Cancel</AppButton>
      </form>
</template>
<script>
import AppButton from "@/components/UI/AppButton";
import AppControlInput from "@/components/UI/AppControlInput";

export default {
  props: {
    post: {
      type: Object,
      required: false
    },
    isAdmin: {
      type: Boolean,
      required: true
    }
  },
  data() {
    return {
      editPost: this.post
        ? { ...this.post }
        : {
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
    AppButton,
    AppControlInput
  }
};
</script>
