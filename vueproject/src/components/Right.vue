<template>
  <div class="good-list">
    <p>==={{kk}}===</p>
    <GoodList :goodId="kk"></GoodList>
  </div>
</template>

<script>
import Msg from "./msg.js";
import GoodList from "./GoodList";
export default {
  data() {
    return {
      kk: 1
    };
  },
  components: { GoodList },
  mounted() {
    Msg.$on("val", v => {
      this.kk = v + 1;
    });
  }
};
</script>

<style lang="less" scoped>
.good-list {
  height: calc(100vh - 200px);
  overflow: scroll;
}
</style>