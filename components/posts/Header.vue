<template>
  <div>
    <!--   ปรับแต่งรูปภาพ -->
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!--    สไลด์ข้อความพร้อมรูปภาพ  -->
      <!--List Rendering  -->
      <div v-for="item in items">
        <b-carousel-slide
          :caption="item.caption"
          :text="item.text"
          :img-src="item.image"
        ></b-carousel-slide>
      </div>
    </b-carousel>
  </div>
</template>
<script>
export default {
  data() {
    return {
      items: [
        {
          caption: "A",
          image: require("@/assets/images/p1.jpg"),
          text: "Nulla vitae elit libero, a pharetra augue mollis interdum.",
        },
        {
          caption: "b",
          image: require("@/assets/images/p2.jpg"),
          text: "Nulla vitae elit libero, a pharetra augue mollis interdum.",
        },
        {
          caption: "c",
          image: require("@/assets/images/p3.jpg"),
          text: "Nulla vitae elit libero, a pharetra augue mollis interdum.",
        },
        {
          caption: "d",
          image: require("@/assets/images/p4.jpg"),
          text: "Nulla vitae elit libero, a pharetra augue mollis interdum.",
        },
      ],
      slide: 0,
      sliding: null,
    };
  },
  methods: {
    onSlideStart(slide) {
      this.sliding = true;
    },
    onSlideEnd(slide) {
      this.sliding = false;
    },
  },
};
</script>