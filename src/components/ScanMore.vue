<template>
  <div class="scan-more-container">
    <a :href="targetUrl" target="_blank">
      <div class="figure">
        <i class="iconfont icon-alipay-arrow-right-circle"></i>
      </div>
      <div class="more">
        {{ title }}
        <small>{{ subTitle }}</small>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: "ScanMore",
  props: {
    targetUrl: String,
    title: {
      type: String,
      // required: true,
      default() {
        return "浏览更多"
      }
    },
    subTitle: {
      type: String,
      default() {
        return "热门"
      }
    },
  }
}
</script>

<style scoped lang="less">
.scan-more-container {
  width: 234px;
  a {
    color: #757575;
    .figure {
      position: absolute;
      right: 35px;
      top: 48px;
      width: 48px;
      height: 48px;
      color: #ff6700;

      i {
        font-size: 48px;
        line-height: 48px;
      }
    }

    .more {
      display: block;
      margin: 0 110px 0 30px;
      font-size: 18px;
      color: #333333;

      small {
        display: block;
        font-size: 12px;
        color: #757575;
        margin-top: 5px;
      }
    }
  }
}
</style>
