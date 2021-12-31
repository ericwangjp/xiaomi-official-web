<template>
  <div class="more-container">
    <ul>
      <li v-for="(item,index) in tabData" :key="item" @mouseenter="enter(index)" :class="{active:curIndex === index}">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MoreTabs",
  props: ['tabData'],
  data() {
    return {
      curIndex: 0
    }
  },
  methods: {
    enter(index) {
      this.curIndex = index
    }
  }
}
</script>

<style scoped lang="less">
.more-container {
  -webkit-font-smoothing: antialiased;
  position: absolute;
  top: 0;
  right: 0;

  ul {
    margin: 0;
    padding: 16px 0 0;
    font-size: 16px;

    li {
      margin: 0 0 0 30px;
      padding: 3px 0;
      display: inline-block;
      cursor: pointer;
      transition: border .3s;
      color: #424242;
      border-bottom: 2px solid rgba(0, 0, 0, 0);
    }
  }

  .active {
    color: #ff6700;
    border-bottom: 2px solid #ff6700;
  }
}
</style>
