<template>
  <div class="main">
    <div class="left">
      <left></left>
    </div>
    <div class="right">
      <div class="top">
        <img src="img/jianzhu/1.png" alt />
      </div>
      <div class="bottom">
        <right />
      </div>
    </div>
  </div>
</template>
 
<script>
import Left from "../components/Left.vue";
import Right from "../components/Right.vue";
export default {
  data() {
    return {
      currentIndex: 0
    };
  },
  components: {
    Left,
    Right
  },
  methods: {
    getValue(data) {
      this.currentIndex = data;
    }
  }
};
</script>

<style lang="less" >
* {
  padding: 0;
  margin: 0;
  list-style: none;
}
.main {
  overflow: hidden;
  width: 100vw;
  height: 100vh;
  .left {
    float: left;
    width: 100px;
    // background: pink;
    height: 100%;
    margin-right: 10px;
  }
  .right {
    float: left;
    width: calc(100vw - 110px);
    height: 100vh;
    background-color: skyblue;
    .top {
      img {
        width: 100%;
        height: 200px;
      }
    }
  }
}
</style>