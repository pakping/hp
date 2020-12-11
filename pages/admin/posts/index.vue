<template>

<PostList isAdmin :posts="loadData"/>
  
</template>

<script>
/* ส่งค่ามาแต่ละหน้า */
import Header from "@/components/posts/Header";
import PostList from "@/components/posts/PostList";
export default {
  layout: "coreLayout",
  components: {
    Header,
    PostList,
  },
};
</script>
