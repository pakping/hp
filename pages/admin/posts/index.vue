<template>
  <div>
    <PostList isAdmin :posts="loadData" />
  </div>
</template>

<script>
/* ส่งค่ามาแต่ละหน้า */

import Header from "@/components/posts/Header";
import PostList from "@/components/posts/PostList";
import axios from "axios";
export default {
  layout: "coreLayout",
  components: {
    Header,
    PostList,
  },
  data() {
    return { loadData: [] };
  },

  methods: {
    async postsAll() {
      console.log("click");
     await this.getData().then((result)=>{
        console.log(result);
      })
      console.log("load complete ...")
    },
    getData() {
      return  new Promise((resolve,reject)=>{
          setTimeout(()=>{
           const data = axios.get("https://hp-up-bc8ae-default-rtdb.firebaseio.com/post.json")
            .then(res => {
              return res
             
          })
         resolve(data) },4000)
        })
    },
  },
};
</script>

