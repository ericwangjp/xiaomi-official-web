<template>
  <div class="video-item-container">
    <a href="javascript:void(0);" title="点击播放视频">
      <div class="img">
        <img :src="imgUrl" :alt="title">
        <span class="play">
          <i class="iconfont icon-alipay-arrow-right"></i>
        </span>
      </div>
      <h3 class="title">{{ title }}</h3>
      <p class="desc">{{ desc }}</p>
    </a>
  </div>
</template>

<script>
export default {
  name: "VideoItem",
  props: {
    imgUrl: {
      type: String,
      default() {
        return "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e74c4ff741bcdfc5b28a48a43e4edc6d.jpg?thumb=1&w=592&h=360&f=webp&q=90"
      }
    },
    title: {
      type: String,
      // required: true,
      default() {
        return "2021年春季新品发布会第一场"
      }
    },
    desc: {
      type: String,
      default() {
        return ""
      }
    }
  }
}
</script>

<style scoped lang="less">
.video-item-container {
  a {
    color: #757575;

    .img {
      position: relative;
      width: 296px;
      height: 180px;
      margin: 0 0 28px;

      img {
        width: 296px;
        height: 180px;
        border: 0;
      }

      .play {
        position: absolute;
        left: 20px;
        bottom: 10px;
        width: 32px;
        height: 20px;
        border: 2px solid #ffffff;
        border-radius: 12px;
        background-color: rgba(0, 0, 0, .6);
        color: white;
        transition: all .2s;
        overflow: hidden;

        i {
          font-size: 20px;
          line-height: 20px;
        }
      }

      &:hover {
        .play {
          border-color: #ff6700;
          background-color: #ff6700;
        }

      }
    }

    .title {
      margin: 0 14px 6px;
      font-size: 14px;
      font-weight: 400;
      text-align: center;
      color: #333333;
      white-space: nowrap;
      text-overflow: ellipsis;
      overflow: hidden;
    }

    .desc {
      height: 18px;
      margin: 14px auto;
      font-size: 12px;
      color: #b0b0b0;
      white-space: nowrap;
      text-overflow: ellipsis;
      overflow: hidden;
    }
  }
}
</style>
