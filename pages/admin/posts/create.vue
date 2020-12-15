<template>
      <AdminForm @sendData="onSubmitted"/>
</template>

<script>
import AdminForm from "@/components/admin/AdminForm";
import axios from 'axios'
export default {
  layout: "coreLayout",
  components: {
    AdminForm,
  },
  methods:{
      onSubmitted(postData){
        axios.post("https://hp-up-bc8ae-default-rtdb.firebaseio.com/post.json",postData)
        .then(res=>{
          console.log(res);
        })
      }
  }
};
</script>
<!-- เชื้่อมกับ AdminForm-->