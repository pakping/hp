<template>
  <b-col md="3">
    <b-card
      :title="title"
      :img-src="image"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem"
      class="mb-2"
    >
      <b-card-text>
        {{ content }}
      </b-card-text>
      <!-- จุดเช็ค สิทธเข้าแต่ละปุ่ม-->
      <nuxt-link class="btn btn-success" :to="postLink">
            {{ isAdmin ? 'แก้ไขบทความ': 'อ่านบทความ' }}
        </nuxt-link>
     
    </b-card>
  </b-col>
</template>
<script>
export default {
  props: {
    id: {
      type: String,
      required: false,
    },
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
    isAdmin: {/* ปรับสิทธ ใน admin */
      type: Boolean,
      required: true,
    },
  },
  computed: {/* คำสังตราจสอยสอบสิทธ */
    postLink() {
      return this.isAdmin ? "/admin/posts/" + this.id : "/posts/" + this.id;
    },
  },
};
</script>

<style scoped>
b-card {
  position: left;
}
</style>>
