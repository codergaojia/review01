<template>
  <div>
    <ul>
      <li v-for="(item, index) in list" :key="index">
        <img :src="item.img" alt />
        <p>{{item.goodName}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: []
    };
  },
  props: ["goodId"],
  created() {
    this.changeData();
  },
  watch: {
    goodId() {
      this.changeData();
    }
  },
  methods: {
    // json请求发生变化
    changeData() {
      console.log(this.$props.goodId);
      let url = `json/${this.$props.goodId}.json`;
      console.log(url);
      this.$http.get(url).then(res => {
        this.list = res.data;
      });
    }
  }
};
</script>

<style lang="less">
.good-list {
  ul {
    overflow: hidden;
    li {
      float: left;
      margin: 10px;
      img {
        width: 180px;
        height: 180px;
      }
    }
  }
}
</style>