<template>
  <div class="title-more-container">
    <h2>{{ title }}</h2>
    <div class="more">
      <a href="https://www.mi.com/p/1915.html">
        {{ moreText }}
        <i class="iconfont icon-alipay-arrow-right"></i>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "TitleMore",
  props: {
    title: {
      type: String,
      // required: true,
      default() {
        return "视频"
      }
    },
    moreText: {
      type: String,
      default() {
        return "查看全部"
      }
    }
  }
}
</script>

<style scoped lang="less">
.title-more-container {
  position: relative;
  height: 58px;
  -webkit-font-smoothing: antialiased;

  h2 {
    margin: 0;
    font-size: 22px;
    font-weight: 400;
    line-height: 58px;
    color: #333333;
  }

  .more {
    position: absolute;
    top: 0;
    right: 0;

    a {
      font-size: 16px;
      line-height: 58px;
      color: #424242;
      transition: all .4s;

      i {
        background: #b0b0b0;
        width: 12px;
        height: 12px;
        padding: 4px;
        margin-left: 8px;
        border-radius: 16px;
        font-size: 12px;
        font-weight: 600;
        line-height: 12px;
        vertical-align: 1px;
        transition: all .4s;
        color: white;
      }

      &:hover {
        color: #ff6700;

        i {
          background-color: #ff6700;
        }
      }
    }
  }
}
</style>
