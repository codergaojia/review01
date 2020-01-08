<template>
  <div>
    <div class="title">热门推荐</div>
    <ul>
      <li v-for="(item, index) in menuArr" :key="index" @click="menu(index)">{{item}}</li>
    </ul>
  </div>
</template>

<script>
import Msg from './msg.js';
export default {
  data() {
    return {
      menuArr: [
        "手机1",
        "手机2",
        "手机3",
        "手机4",
        "手机5",
        "手机6",
        "手机7",
        "手机8"
      ],
    }
  },
  methods: {
    menu(index) {
      Msg.$emit("val",index)
    }
  }
};
</script>
<style lang="less" scoped >
.title {
  width: 100px;
  color: red;
  background-color: #cccccc;
  line-height: 40px;
}
li {
  line-height: 40px;
  border-top: 1px solid #dddddd;
  cursor: pointer;
}
</style>