<template>
  <div class="home-banner-container">
    <div class="home-hero">
      <div class="swiper-container">
        <!--        <div class="swiper-wrapper"></div>-->
        <!--        <div class="swiper-pagination"></div>-->
        <!--        <div class="swiper-button-prev"></div>-->
        <!--        <div class="swiper-button-next"></div>-->
        <!--        <div class="swiper-notification"></div>-->
        <el-carousel height="460px">
          <el-carousel-item v-for="item in bannerList" :key="item">
            <el-image
                :src="item"
                fit="fill"></el-image>
          </el-carousel-item>
        </el-carousel>
      </div>
      <div class="home-hero-sub clearfix">
        <div class="span4">
          <ul class="home-channel-list clearfix">
            <li v-for="(item,index) in channelList" :key="index">
              <a href="javascript:;">
                <img :src="item.imageUrl"
                     :alt="item.name">
                {{ item.name }}
              </a>
            </li>
          </ul>
        </div>
        <div class="span16">
          <ul class="home-promo-list clearfix">
            <li v-for="(item,index) in promoList" :key="index">
              <a :href="item.targetUrl">
                <img :src="item.imageUrl" alt="">
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeBanner",
  data() {
    return {
      bannerList: [
        "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/78d0483ed36158659fcf65a19a9b249a.jpeg?w=2452&h=920",
        "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/fc0f553382bb5143e667b284dfcf02db.jpg?thumb=1&w=2452&h=920&f=webp&q=90",
        "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/918820682e4a490221cfd92b24c14b86.jpg?thumb=1&w=2452&h=920&f=webp&q=90"
      ],
      channelList: [
        {
          name: "保障服务",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/82abdba456e8caaea5848a0cddce03db.png?w=48&h=48"
        },
        {
          name: "企业团购",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/806f2dfb2d27978e33fe3815d3851fa3.png?w=48&h=48"
        },
        {
          name: "F码通道",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/eded6fa3b897a058163e2485532c4f10.png?w=48&h=48"
        },
        {
          name: "米粉卡",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/43a3195efa6a3cc7662efed8e7abe8bf.png?w=48&h=48"
        },
        {
          name: "依旧换新",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/f4846bca6010a0deb9f85464409862af.png?w=48&h=48"
        },
        {
          name: "话费充值",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/9a76d7636b08e0988efb4fc384ae497b.png?w=48&h=48"
        },
      ],
      promoList: [
        {
          targetUrl: "https://www.mi.com/mi11ultra",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/d8a6d6d37904e22c72130e3e4ec79b41.jpg?w=632&h=340"
        },
        {
          targetUrl: "https://www.mi.com/mixfold",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/fce474f4024b96545959ccd45b7e50f3.jpg?w=632&h=340"
        },
        {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14903",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/35b3f906861db9d6472206e6d68318d9.jpeg?w=632&h=340"
        }
      ]
    }
  }
}
</script>

<style scoped lang="less">
.home-banner-container {
  position: relative;
  z-index: 10;
  width: 1226px;
  margin: 0 auto;

  .home-hero {
    position: relative;
    margin-bottom: 26px;

    .swiper-container {
      position: relative;
      height: 460px;
      overflow: hidden;
      margin: 0 auto;

      .el-carousel {
        position: relative;

        /deep/ .el-carousel__arrow--left {
          margin-left: 240px;
          //left: 200px;
        }

        /deep/ .el-carousel__indicators {
          position: absolute;
          left: auto;
          right: 30px;
          bottom: 20px;
          transition: opacity .3s;
          text-align: right;

          .el-carousel__indicator {
            padding: 0;
            margin: 0 4px;
            width: 6px;
            height: 6px;
            border-radius: 10px;
            border: 2px solid #fff;
            border-color: hsla(0, 0%, 100%, .3);
            overflow: hidden;
            background: rgba(0, 0, 0, .4);
            opacity: 1;

            .el-carousel__button {
              width: 6px;
              height: 6px;
              overflow: hidden;
              background: rgba(0, 0, 0, .4);
            }
          }

          .is-active {
            background: hsla(0, 0%, 100%, .4);
            border-color: rgba(0, 0, 0, .4);

            .el-carousel__button {
              background: hsla(0, 0%, 100%, .4);
            }
          }

        }
      }
    }

    .home-hero-sub {
      margin-top: 14px;
      margin-left: -14px;

      .span4 {
        width: 234px;
        float: left;
        margin-left: 14px;
        min-height: 1px;

        .home-channel-list {
          margin: 0;
          padding: 3px;
          font-size: 12px;
          text-align: center;
          background: #5f5750;

          li {
            position: relative;
            float: left;
            width: 70px;
            height: 82px;
            padding: 0 3px;

            &:after {
              top: 6px;
              left: 0;
              width: 1px;
              height: 70px;
              position: absolute;
              content: "";
              background: #665e57;
            }

            &:before {
              top: -1px;
              left: 6px;
              width: 64px;
              height: 1px;
              position: absolute;
              content: "";
              background: #665e57;
            }

            a {
              display: block;
              padding-top: 18px;
              text-overflow: ellipsis;
              color: white;
              opacity: .7;
              transition: opacity .2s;

              &:hover {
                opacity: 1;
              }

              img {
                display: block;
                width: 24px;
                height: 24px;
                margin: 0 auto 4px;
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

        .home-promo-list {
          margin: 0;
          padding: 0;
          list-style-type: none;

          > li:first-child {
            margin-left: 0;
          }

          li {
            float: left;
            width: 316px;
            height: 170px;
            margin-left: 15px;
            transition: box-shadow .2s linear;

            &:hover {
              -webkit-box-shadow:0 15px 30px rgba(0, 0, 0, .1);
              box-shadow:0 15px 30px rgba(0, 0, 0, .1);
              z-index: 2;
            }

            a {
              display: block;
              height: 170px;
              color: #757575;
              background: url("https://i1.mifile.cn/f/i/2014/cn/placeholder-80.png") no-repeat 50%;

              img {
                display: block;
                width: 316px;
                height: 170px;
                border: 0;
              }
            }
          }
        }
      }
    }
  }
}
</style>
