<template>
  <div class="top-container">
    <div class="top-bar">
      <div class="left">
        <ul>
          <li v-for="(item,index) in navItems" :key="index">
            <a :href="item.url">{{ item.name }}</a>
            <span class="sep">|</span>
          </li>
        </ul>
      </div>

      <div class="cart">
        <a href="javascript:;">
          <em class="iconfont icon-alipay-cart-empty"></em>
          <em class="iconfont icon-alipay-cart hide"></em>
          购物车
          <span class="cart-num">(0)</span>
        </a>
        <div class="cart-list-menu">
          <div class="cart-list-box">
            <div class="loading">
              <div class="loader hide"></div>
              <ul class="cart-list hide"></ul>
              <div id="cart-list-total" class="cart-total clearfix hide"></div>
              <div class="msg msg-error hide"></div>
              <div class="msg msg-empty ">购物车中还没有商品，赶紧选购吧！</div>
            </div>
          </div>
        </div>
      </div>

      <div class="right">
        <ul>
          <li v-for="(loginItem,index) in loginItems" :key="index">
            <a :href="loginItem.url">{{ loginItem.name }}</a>
            <span class="sep">|</span>
          </li>
        </ul>
      </div>

      <div class="download">
        <a href="javascript:;" @mouseenter="showQrCode" @mouseleave="hideQrCode" ref="download"
           :class="{active:qrCodeVisible}">
          下载APP
          <span class="qrcode">
            <img src="https://i1.mifile.cn/f/i/17/appdownload/download.png?1" alt="小米商城">
            小米商城APP
          </span>
        </a>
        <span class="sep">|</span>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "TopBar",
  data() {
    return {
      navItems: [
        {name: '小米商城', url: 'https://www.mi.com/index.html'},
        {name: 'MIUI', url: 'http://www.miui.com/'},
        {name: '米聊', url: 'http://www.miliao.com/'},
        {name: '游戏', url: 'http://game.xiaomi.com/hy/index.html'},
        {name: '多看阅读', url: 'http://www.duokan.com/'},
        {name: '云服务', url: 'https://i.mi.com/'},
        {name: '金融', url: 'https://jr.mi.com/?from=micom'},
        {name: '小米商城', url: 'https://www.mi.com/appdownload/'},
        {name: '问题反馈', url: 'https://static.mi.com/feedback/'},
        {name: 'Select Region', url: 'https://www.mi.com/#J_modal-globalSites'}
      ],
      loginItems: [
        {name: '登录', url: 'https://order.mi.com/site/login?redirectUrl=https://www.mi.com/'},
        {name: '注册', url: 'https://account.xiaomi.com/pass/register'},
        {name: '消息通知', url: 'https://order.mi.com/message/list'}
      ],
      cartStatus: false,
      qrCodeVisible: false
    }
  },
  methods: {
    showQrCode() {
      this.qrCodeVisible = true
    },
    hideQrCode() {
      this.qrCodeVisible = false
    }
  }
}
</script>

<style scoped lang="less">

.top-container {
  width: 100%;
  background: #333;

  .top-bar {
    width: 100%;
    height: 40px;
    line-height: 40px;
    position: relative;
    background: #333;
    color: #b0b0b0;
    font-size: 12px;
    z-index: 30;
    max-width: 1226px;
    margin: 0 auto;
    padding: 0;

    .left {
      float: left;
      line-height: 40px;

      ul {
        display: flex;

        li {
          &:last-child .sep {
            display: none;
          }

          a {
            color: #b0b0b0;
            line-height: 40px;
            display: inline-block;
            text-decoration: none;

            &:hover {
              color: white;
            }
          }

          .sep {
            margin: 0 0.3em;
            color: #424242;
          }
        }
      }
    }

    .right {
      position: relative;
      float: right;
      height: 40px;
      line-height: 40px;

      ul {
        display: flex;

        li {
          float: left;

          &:last-child .sep {
            display: none;
          }

          a {
            padding: 0 5px;
            text-align: center;
            color: #b0b0b0;
            line-height: 40px;
            display: inline-block;

            &:hover {
              color: white;
            }
          }

          .sep {
            margin: 0;
            color: #424242;
          }
        }

      }
    }

    .cart {
      position: relative;
      float: right;
      width: 120px;
      height: 40px;
      margin-left: 15px;
      -webkit-transition: all .2s;
      transition: all .2s;
      font-size: 12px;

      &:hover {
        a {
          color: #ff6700;
          background-color: white;
        }

        .cart-list-menu {
          height: 100px;

        }
      }

      a {
        text-decoration: none;
        position: relative;
        z-index: 32;
        display: block;
        height: 40px;
        line-height: 40px;
        text-align: center;
        color: #b0b0b0;
        background: #424242;

        em {
          margin-right: 4px;
          font-size: 20px;
          line-height: 20px;
          vertical-align: -4px;
        }

      }

      .cart-list-menu {
        position: absolute;
        right: 0;
        top: 40px;
        z-index: 31;
        width: 316px;
        height: 0;
        color: #424242;
        background: #fff;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        overflow: hidden;
        -webkit-transition: height .3s;
        transition: height .3s;

        .cart-list-box {
          padding: 20px 0 0;
          box-sizing: border-box;

          .loading {
            padding: 20px 0;
            text-align: center;

            .loader {
              position: relative;
              margin: 0 auto;
              width: 4px;
              height: 20px;
              background: #ff6700;
              overflow: visible;
              -webkit-animation-delay: 0s;
              animation-delay: 0s;
              -webkit-transform: scale(1);
              -ms-transform: scale(1);
              transform: scale(1);
              -webkit-transform-origin: 50% 50%;
              -ms-transform-origin: 50% 50%;
              transform-origin: 50% 50%;
              -webkit-animation-name: loader;
              animation-name: loader;
              -webkit-animation-duration: .3s;
              animation-duration: .3s;
              -webkit-animation-timing-function: linear;
              animation-timing-function: linear;
              -webkit-animation-iteration-count: infinite;
              animation-iteration-count: infinite;
              animation-direction: alternate-reverse;

              &:before, &:after {
                -webkit-transform-origin: 50% 50%;
                -ms-transform-origin: 50% 50%;
                transform-origin: 50% 50%;
                -webkit-animation-name: loader;
                animation-name: loader;
                -webkit-animation-duration: .3s;
                animation-duration: .3s;
                -webkit-animation-timing-function: linear;
                animation-timing-function: linear;
                -webkit-animation-iteration-count: infinite;
                animation-iteration-count: infinite;
                animation-direction: alternate-reverse;
              }
            }

            .cart-list {
              margin: 0;
              padding: 0;
              list-style-type: none;

              .cart-total {
                padding: 15px 20px;
                background: #fafafa;
              }

              .msg {
                padding: 20px 0 20px;
                margin: 0 20px 20px;
                text-align: center;
              }
            }
          }
        }
      }
    }

    .download {
      position: relative;
      float: right;

      a {
        color: #b0b0b0;
        line-height: 40px;
        display: inline-block;
        margin-right: 4px;
        display: inline-block;
        position: relative;

        &:hover {
          color: white;
        }

        .qrcode {
          position: absolute;
          top: 40px;
          left: 50%;
          width: 124px;
          height: 0;
          background: white;
          margin-left: -55px;
          box-shadow: 0 1px 5px #aaa;
          text-align: center;
          font-size: 14px;
          color: #333333;
          line-height: 1;
          overflow: hidden;
          transition: height .3s;

          //&:hover {
          //  height: 148px !important;
          //}

          img {
            display: block;
            margin: 18px auto 12px;
            width: 90px;
            height: 90px;
            aspect-ratio: auto 90/90;
          }
        }
      }

      .sep {
        margin: 0 0.3em;
        color: #424242;
      }

      .active {
        .qrcode {
          height: 148px !important;
        }

        &::before {
          content: "";
          position: absolute;
          bottom: 0;
          left: 50%;
          width: 0;
          height: 0;
          margin-left: -8px;
          border-width: 0 8px 8px;
          border-style: solid;
          border-color: rgba(0, 0, 0, 0) rgba(0, 0, 0, 0) #fff;
        }
      }

    }
  }
}
</style>
