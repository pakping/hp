<template>
  <b-row class="py-5">
    <!-- แบ่งช่องว่างระว่าง header -->
    <!-- link-> components/posts/postcomponents -->
    <PostContent
      v-for="post in posts"
      :key="post.id"
      :id="post.id"
      :title="post.title"
      :content="post.content"
      :image="post.image"
      :isAdmin="isAdmin"
    />
  </b-row>
</template>
<script>
import Postcomponents from "@/components/posts/Postcomponents";
export default {
  Content: {
    Postcomponents,
  },
  /* ตรวจสอบสิทธ */
  props: {
    isAdmin: {
      type: Boolean,
      required: false,
    },
    posts: {
      type: Array /* จุดประมาลผล */,
      required: true,
    },
  },
};
</script>>