<template>
  <div class="home-tool-bar-container home-tool-bar-small mini">
    <a href="javascript:;" class="item" v-for="(item,index) in toolbarList" :key="item.tipText"
       :class="{'item-image':index===0,'back-top':index===toolbarList.length-1,'active':isActive}"
       @click="backToTop(index)">
      <div class="icon">
        <img :src="item.imgNormal" alt="" class="static">
        <img :src="item.imgHover" alt="" class="hover">
      </div>
      <span class="text">{{ item.tipText }}</span>
      <div class="pop-content clearfix" v-if="index === 0">
        <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/78c30d4f259ed43ab20e810a522a6249.png" alt="">
        <span class="desc"> 扫码领取新人百元礼包 </span>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: "HomeToolBar",
  data() {
    return {
      toolbarList: [
        {
          imgNormal: "https://i8.mifile.cn/b2c-mimall-media/98a23aae70f25798192693f21c4d4039.png",
          imgHover: "https://i8.mifile.cn/b2c-mimall-media/74c4fcb4475af8308e9a670db9c01fdf.png",
          tipText: "手机APP"
        }, {
          imgNormal: "https://i8.mifile.cn/b2c-mimall-media/55cad219421bee03a801775e7309b920.png",
          imgHover: "https://i8.mifile.cn/b2c-mimall-media/41f858550f42eb1770b97faf219ae215.png",
          tipText: "个人中心"
        }, {
          imgNormal: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/12eb0965ab33dc8e05870911b90f3f13.png",
          imgHover: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/95fbf0081a06eec7be4d35e277faeca0.png",
          tipText: "售后服务"
        }, {
          imgNormal: "https://i8.mifile.cn/b2c-mimall-media/4f036ae4d45002b2a6fb6756cedebf02.png",
          imgHover: "https://i8.mifile.cn/b2c-mimall-media/5e9f2b1b0da09ac3b3961378284ef2d4.png",
          tipText: "人工客服"
        }, {
          imgNormal: "https://i8.mifile.cn/b2c-mimall-media/d7db56d1d850113f016c95e289e36efa.png",
          imgHover: "https://i8.mifile.cn/b2c-mimall-media/692a6c3b0a93a24f74a29c0f9d68ec71.png",
          tipText: "购物车"
        }, {
          imgNormal: "https://i1.mifile.cn/f/i/2018/home/totop.png",
          imgHover: "https://i1.mifile.cn/f/i/2018/home/totop_hover.png",
          tipText: "回顶部"
        },
      ],
      isActive: false,
      time: null
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScrollEvent)
  },
  methods: {
    handleScrollEvent(e) {
      console.log(e)
      if (document.documentElement.scrollTop > 100) {
        this.isActive = true
      } else {
        this.isActive = false
      }
    },
    backToTop(index) {
      if (index === this.toolbarList.length - 1) {
        document.documentElement.scrollTop = 0;
        // document.documentElement.scrollTop -= 5;
        // if (document.documentElement.scrollTop > 0) {
        //   this.time = setTimeout(() => this.backToTop(), 5000);
        // } else {
        //   clearTimeout(this.time)
        // }
      }
    }
  }
}
</script>

<style scoped lang="less">
.home-tool-bar-container {
  right: 0;
  bottom: 70px;
  z-index: 99;
  position: fixed;

  .item {
    position: relative;
    display: block;
    width: 82px;
    height: 90px;
    margin-top: -1px;
    background-color: #fff;
    border: 1px solid #f5f5f5;
    text-align: center;

    &:hover {
      .text {
        color: #ff6700;
      }

      .icon {
        .static {
          opacity: 0;
        }

        .hover {
          opacity: 1;
        }
      }

      .pop-content {
        transform: translate3d(-110%, 0, 0);
        opacity: 1;
        visibility: visible;
      }
    }

    .icon {
      position: relative;
      width: 30px;
      height: 30px;
      margin: 0 auto 8px;
      padding-top: 18px;

      img {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 30px;
        height: 30px;
        transition: opacity .3s;
      }

      .static {
        opacity: 1;
      }

      .hover {
        opacity: 0;
      }
    }

    .text {
      color: #757575;
      transition: color .3s;
    }

    .pop-content {
      position: absolute;
      left: 0;
      top: 0;
      padding: 14px;
      background: white;
      border: 1px solid #f5f5f5;
      transition: opacity .3s;
      transform: translateZ(0);
      opacity: 0;
      visibility: hidden;

      &:before,
      &:after {
        content: "";
        position: absolute;
        top: 21%;
        width: 0;
        height: 0;
        border-width: 10px;
        border-style: solid;
        overflow: hidden;
      }

      &:before {
        right: -19px;
        border-color: rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) #f5f5f5;
        z-index: 1
      }

      &:after {
        right: -18px;
        border-color: rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) #fff;
        z-index: 2;
      }

      img {
        display: block;
        width: 100px;
        height: 100px;
        margin: 6px auto;
      }

      .desc {
        display: block;
        width: 82px;
        margin: 14px auto 0;
        color: #757575;
        text-align: center;
      }
    }
  }

  .back-top {
    margin-top: 14px;
    border-top: 1px solid #f5f5f5;
    visibility: hidden;

    &.active {
      visibility: visible;
    }
  }
}

// 小屏幕侧边工具栏适配
@media only screen and (max-width: 1600px) {

  .home-tool-bar-small {
    left: 50%;
    right: auto;
    margin-left: 613px;
    bottom: 40px;

    &.mini {
      right: 0;
      left: auto;
      margin-left: 0;
    }

    // 不可嵌套，否则无效
    //@media only screen and (min-width: 1200px) {
    //.home-tool-bar-small{
    //  &.mini {
    //    right: 60px;
    //    left: auto;
    //    margin-left: 0;
    //  }
    //}
    //}

    .item {
      width: 25px;
      height: 40px;

      &:hover {
        .text {
          display: block;
          transform: translate3d(-115%, -50%, 0);
          color: #757575;
        }
      }

      .text {
        display: none;
        position: absolute;
        left: 0;
        top: 50%;
        height: 28px;
        line-height: 28px;
        padding: 0 8px;
        background-color: #fff;
        border: 1px solid #f5f5f5;
        text-align: center;
        white-space: nowrap;

        &:after,
        &:before {
          content: "";
          position: absolute;
          top: 50%;
          width: 0;
          height: 0;
          margin-top: -6px;
          border-width: 6px;
          border-style: solid;
          overflow: hidden;
        }

        &:before {
          border-color: rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) #f5f5f5;
          right: -13px;
          z-index: 1
        }

        &:after {
          border-color: rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) #fff;
          right: -12px;
          z-index: 2
        }
      }

      .icon {
        width: 20px;
        height: 20px;
        padding-top: 10px;

        img {
          width: 20px;
          height: 20px;
        }
      }

      .pop-content {

        &:before,
        &:after {
          top: 10px;
          border-width: 6px;
        }

        &:before {
          right: -13px;
        }

        &:after {
          right: -12px;
        }
      }
    }

    .item-image {
      &:hover {
        .text {
          display: none;
        }
      }
    }
  }
}

</style>
