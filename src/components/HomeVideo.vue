<template>
  <div class="video-container clearfix">
    <title-more/>
    <div class="box-body clearfix">
      <ul class="video-list clearfix">
        <li class="video-item" v-for="item in videos" :key="item.title">
          <video-item v-bind="item"/>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import TitleMore from "@/components/TitleMore";
import VideoItem from "@/components/VideoItem";

export default {
  name: "HomeVideo",
  components: {VideoItem, TitleMore},
  data() {
    return {
      videos: [
        {
          imgUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e74c4ff741bcdfc5b28a48a43e4edc6d.jpg?thumb=1&w=592&h=360&f=webp&q=90",
          title: "2021年春季新品发布会第一场",
          desc: ""
        }, {
          imgUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/101b19aca4bb489bcef0f503e44ec866.jpg?thumb=1&w=592&h=360&f=webp&q=90",
          title: "Redmi 10X系列发布会",
          desc: "Redmi 10X系列发布会"
        }, {
          imgUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/96563e75833ba4563bd469dd28203b09.jpg?thumb=1&w=592&h=360&f=webp&q=90",
          title: "小米10 青春版 发布会",
          desc: ""
        }, {
          imgUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/2fd26bb99b723337a2f8eaba84f7d5bb.jpg?thumb=1&w=592&h=360&f=webp&q=90",
          title: "小米10 8K手机拍大片",
          desc: ""
        }
      ]
    }
  }
}
</script>

<style scoped lang="less">
.video-container {
  .box-body {
    .video-list {
      width: 1240px;
      height: 285px;
      margin: 0;
      padding: 0;
      list-style-type: none;

      .video-item {
        position: relative;
        float: left;
        width: 296px;
        height: 285px;
        margin-left: 14px;
        margin-bottom: 14px;
        text-align: center;
        background: white;
        transition: all .2s linear;

        &:first-child {
          margin-left: 0;
        }

        &:hover {
          z-index: 2;
          box-shadow: 0 15px 30px rgba(0, 0, 0, .1);
          transform: translate3d(0, -2px, 0);
        }
      }
    }
  }
}
</style>
