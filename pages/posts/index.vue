<template>
  <!-- คำสั่งจัดหน้า แล้วเว้นขอบ -->
  <b-container fluid="lg">
    <Header />
    <postList :posts="loadData" />
  </b-container>
</template>
<script>
import Header from "@/components/posts/Header";
import PostList from "@/components/posts/PostList";
export default {
  layout: "coreLayout",
  components: {
    Header,
    PostList,
  },
  data() {
    return {
    loadData: [
      {
        id:"1",
        title:"เทียภูเข้า",
        content:"love is ",
        image:"https://images.unsplash.com/photo-1492691527719-9d1e07e534b4?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1351&q=80",
      },
    ]
    }
  },
};
</script>
