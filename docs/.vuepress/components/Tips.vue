<template>
  <div class="tip">
    <div class="left"><img :src="imgSrc"></div>
    <div class="right">
      <p>
        <slot name="source"></slot>
      </p>
      <p>
        <slot></slot>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["tips"],
  data() {
    return {
      imgSrc: ""
    };
  },
  created() {
    this.chooseTip();
  },
  methods: {
    chooseTip() {
      if (this.tips === "blue") {
        this.imgSrc = "./note.png";
      } else if (this.tips === "green") {
        this.imgSrc = "./tip.png";
      } else if (this.tips === "orange") {
        this.imgSrc = "./warn.png";
      }
    }
  }
};
</script>

<style scoped>
.tip {
  display: flex;
  padding: 16px;
  width: 100%;
}
.left {
  float: left;
  width: 12%;
}
.right {
  float: right;
  padding-left: 16px;
  width: 88%;
}
p { 
  overflow-wrap: break-word;
  margin: 0
}
</style>