<template>
  <div class="mobile-container">
    <div class="box-header">
      <h2>手机</h2>
      <div class="more">
        <a href="https://www.mi.com/p/1915.html">
          查看更多
          <i class="iconfont icon-alipay-arrow-right"></i>
        </a>
      </div>
    </div>
    <div class="box-body clearfix">
      <div class="row">
        <div class="span4">
          <ul class="phone-poster clearfix">
            <li class="phone-poster-item">
              <a href="https://www.mi.com/mixfold">
                <img
                    src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/c583f2edc613f1be20fa415910b13ce3.jpg?thumb=1&w=468&h=1228&f=webp&q=90"
                    alt="">
              </a>
            </li>
          </ul>
        </div>
        <div class="span16">
          <ul class="phone-list clearfix">
            <li class="phone-list-item" v-for="(item,index) in goodsList" :key="index">
              <goods-item :goods-info="item"/>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GoodsItem from "@/components/GoodsItem";

export default {
  name: "MobilePlate",
  components: {GoodsItem},
  data() {
    return {
      goodsList: [
        {
          targetUrl: "https://www.mi.com/redminote11pro",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6d0a3e7acc3e91e2cfd83dbbe1d1c029.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 Pro系列',
          goodsDesc: 'Redmi Note 11 Pro系列',
          goodsPrice: '1799',
          type:1
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/50da95e9e4496dcac8704da2deb94f6e.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 5G',
          goodsDesc: '5000mAh大电量',
          goodsPrice: '1199',
          type:1
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/50da95e9e4496dcac8704da2deb94f6e.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 5G',
          goodsDesc: '5000mAh大电量',
          goodsPrice: '1199',
          type:1
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/50da95e9e4496dcac8704da2deb94f6e.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 5G',
          goodsDesc: '5000mAh大电量',
          goodsPrice: '1199',
          type:1
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/50da95e9e4496dcac8704da2deb94f6e.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 5G',
          goodsDesc: '5000mAh大电量',
          goodsPrice: '1199',
          type:1
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/50da95e9e4496dcac8704da2deb94f6e.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 5G',
          goodsDesc: '5000mAh大电量',
          goodsPrice: '1199',
          type:1
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/50da95e9e4496dcac8704da2deb94f6e.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 5G',
          goodsDesc: '5000mAh大电量',
          goodsPrice: '1199',
          type:1
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/50da95e9e4496dcac8704da2deb94f6e.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi Note 11 5G',
          goodsDesc: '5000mAh大电量',
          goodsPrice: '1199',
          type:1
        }
      ]
    }
  }
}
</script>

<style scoped lang="less">
.mobile-container {
  margin-bottom: 8px;

  .box-header {
    position: relative;
    height: 58px;
    -webkit-font-smoothing: antialiased;

    h2 {
      margin: 0;
      font-size: 22px;
      font-weight: 200;
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

  .box-body {
    .row {
      //margin-left: -14px;

      .span4 {
        width: 234px;
        float: left;
        //margin-left: 14px;
        min-height: 1px;

        .phone-poster {
          margin: 0 0 -14px -14px;
          height: 614px;
          padding: 0;

          .phone-poster-item {
            height: 614px;
            position: relative;
            z-index: 1;
            float: left;
            width: 234px;
            margin-left: 14px;
            margin-bottom: 14px;
            background: white;
            transition: all .2s linear;

            &:hover {
              z-index: 2;
              box-shadow: 0 15px 30px rgba(0, 0, 0, .1);
              transform: translate3d(0, -2px, 0);
            }

            a {
              display: block;
              width: 100%;
              height: 100%;

              img {
                height: 614px;
                width: 234px;
                border: 0;
              }
            }
          }
        }
      }

      .span16 {
        width: 978px;
        float: left;
        margin-left: 14px;
        min-height: 1px;

        .phone-list {
          margin: 0 0 -14px -14px;
          width: 992px;
          height: 614px;
          padding: 0;

          .phone-list-item {
            height: 300px;
            padding: 0;
            position: relative;
            z-index: 1;
            float: left;
            width: 234px;
            margin-left: 14px;
            margin-bottom: 14px;
            background: white;
            transition: all .2s linear;

            &:hover {
              z-index: 2;
              box-shadow: 0 15px 30px rgba(0, 0, 0, .1);
              transform: translate3d(0, -2px, 0);
            }

            a {
              display: block;
              height: 100%;
              box-sizing: border-box;
              padding: 20px 0;

              .figure {
                width: 160px;
                height: 160px;
                margin: 0 auto 18px;

                img {
                  border: 0;
                  width: 160px;
                  height: 160px;
                }
              }

              .title {
                margin: 0 10px 2px;
                text-align: center;
                text-overflow: ellipsis;
                white-space: nowrap;
                overflow: hidden;
                font-size: 14px;
                font-weight: 400;
                color: #333333;
              }

              .desc {
                margin: 0 10px 10px;
                height: 18px;
                line-height: 18px;
                font-size: 12px;
                color: #b0b0b0;
                text-align: center;
                text-overflow: ellipsis;
                white-space: nowrap;
                overflow: hidden;
              }

              .price {
                margin: 0 10px 14px;
                text-align: center;
                color: #ff6700;
              }
            }
          }
        }
      }
    }
  }
}
</style>
