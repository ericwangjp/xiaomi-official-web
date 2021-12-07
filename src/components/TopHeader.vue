<template>
  <div class="top-header">
    <div class="header-title">
      <!--      logo-->
      <div class="header-logo">
        <a href="javascript:;"></a>
      </div>
      <!--      顶部菜单-->
      <div class="header-nav">
        <ul class="header-nav-list">
          <li v-for="(item,index) in headItems" :key="index" class="nav-item">
            <a href="javascript:;" class="link" @mouseenter="enter(index)" @mouseleave="leave">
              <span class="text">{{ item.name }}</span>
            </a>
            <div class="item-children">
              <div class="container">
                <ul class="children-list">
                  <li>
                    <a href="javascript:;">
                      <div class="goods-img">
                        <img
                            src="	https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8cad7…bc2ddfced7c56.png?thumb=1&w=320&h=220&f=webp&q=90"
                            alt="">
                      </div>
                      <div class="goods-title">
                        XiaoMi Civi
                      </div>
                      <p class="price">2599元起</p>
                    </a>
                  </li>
                </ul>
              </div>
            </div>
          </li>
        </ul>
      </div>
      <!-- 搜索-->
      <div class="header-search">
        <form action="" class="search-form clearfix">
          <label for="search" class="hide">站内搜索</label>
          <a href="javascript:;" class="no-style-msg">
            <input type="search" id="search" name="keyword" autocomplete="off" class="search-text" placeholder="手机"
                   @focus="searchFocus=true" @blur="searchFocus=false" :class="{'orange-border':searchFocus}">
          </a>
          <a href="javascript:;" class="no-style-msg">
            <input type="submit" class="search-btn iconfont icon-alipay-search" :class="{'orange-border':searchFocus}"
                   :value="'\ue63d'">
          </a>
          <div class="search-hot-words">

          </div>
          <div class="keyword-list" :class="{hide:!searchFocus}">
            <ul class="result-list">
              <li v-for="(item,index) in searchKeywords" :key="index">
                <a href="javascript:;">{{ item }}</a>
              </li>
            </ul>
          </div>
        </form>
      </div>
    </div>
    <!--title hover动态展示区-->
    <div class="sub-menu" :class="{'header-nav-menu-active':isDown,'slide-down':isDown}">
      <div class="container">
        <ul class="children-list">
          <li v-for="(item,index) in goodsInfo" :key="index">
            <a href="javascript:;">
              <div class="figure">
                <img :src="item.url" alt="">
              </div>
              <div class="title">{{ item.name }}</div>
              <p class="price">{{ item.price }}</p>
            </a>
          </li>
        </ul>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "TopHeader",
  data() {
    return {
      headItems: [
        {name: '小米手机', url: 'https://www.mi.com/index.html'},
        {name: '红米', url: 'https://www.mi.com/index.html'},
        {name: '电视', url: 'https://www.mi.com/index.html'},
        {name: '笔记本', url: 'https://www.mi.com/index.html'},
        {name: '平板', url: 'https://www.mi.com/index.html'},
        {name: '家电', url: 'https://www.mi.com/index.html'},
        {name: '路由器', url: 'https://www.mi.com/index.html'},
        {name: '服务', url: 'https://www.mi.com/index.html'},
        {name: '社区', url: 'https://www.mi.com/index.html'},
      ],
      searchKeywords: [
        "手机", "小米平板5 Pro", "洗衣机", "耳机", "电视", "加湿器", "空调"
      ],
      goodsInfo: [
        {
          name: 'XiaoMi Civi',
          price: '2599元起',
          url: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8cad77bda138fd94eadbc2ddfced7c56.png?thumb=1&w=320&h=220&f=webp&q=90'
        }, {
          name: 'XiaoMi Note9',
          price: '1599元起',
          url: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8cad77bda138fd94eadbc2ddfced7c56.png?thumb=1&w=320&h=220&f=webp&q=90'
        },
        {
          name: 'XiaoMi 10',
          price: '2599元起',
          url: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8cad77bda138fd94eadbc2ddfced7c56.png?thumb=1&w=320&h=220&f=webp&q=90'
        }, {
          name: 'XiaoMi 11',
          price: '1599元起',
          url: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8cad77bda138fd94eadbc2ddfced7c56.png?thumb=1&w=320&h=220&f=webp&q=90'
        },
        {
          name: 'XiaoMi Note10',
          price: '2599元起',
          url: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8cad77bda138fd94eadbc2ddfced7c56.png?thumb=1&w=320&h=220&f=webp&q=90'
        }, {
          name: 'XiaoMi Note11',
          price: '1599元起',
          url: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8cad77bda138fd94eadbc2ddfced7c56.png?thumb=1&w=320&h=220&f=webp&q=90'
        }
      ],
      isDown: false,
      searchFocus: false,
      curIndex:-1
    }
  },
  methods: {
    enter(index) {
      this.isDown = true
      this.curIndex = index
    },
    leave() {
      this.isDown = false
    }
  }
}
</script>

<style scoped lang="less">

.top-header {
  width: 100%;
  position: relative;
  z-index: 20;
  height: 100px;
  margin: 0 auto;

  .header-title {
    position: relative;
    width: 1226px;
    margin: 0 auto;

    .header-logo {
      position: relative;
      float: left;
      width: 62px;
      margin-top: 22px;

      a {
        position: relative;
        display: block;
        width: 56px;
        height: 56px;
        overflow: hidden;
        text-align: center;
        text-indent: -9999em;

        &:before {
          position: absolute;
          left: 0;
          top: 0;
          z-index: 1;
          width: 56px;
          height: 56px;
          content: "";
          background: url("https://s02.mifile.cn/assets/static/image/logo-mi2.png") no-repeat;
          background-size: 56px;
          opacity: 1;
          transform: translateZ(0);
          transform-origin: 50% 50%;
        }

      }
    }

    .header-nav {
      float: left;
      width: 850px;

      .header-nav-list {
        position: relative;
        z-index: 10;
        float: left;
        width: 1100px;
        height: 88px;
        margin: 0 auto;
        padding: 12px 0 0 30px;
        list-style-type: none;
        font-size: 16px;

        .nav-item {
          float: left;
          display: list-item;

          .link {
            display: block;
            padding: 26px 10px 38px;
            color: #333333;
            transition: color .2s;

            &:hover {
              color: #ff6700;
            }
          }

          .item-children {
            display: none;

            .container {
              position: relative;
              width: 1226px;
              margin: 0 auto;

              .children-list {
                list-style-type: circle;
                margin-block-start: 0;
                margin-block-end: 0;

                a {
                  color: #757575;

                  .goods-img {
                    img {
                      border: 0;
                      width: 160px;
                      aspect-ratio: auto 160/110;
                      height: 110px;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }

    .header-search {
      float: right;
      width: 296px;
      margin-top: 25px;
      display: block;
      box-sizing: border-box;

      .search-form {
        position: relative;
        width: 296px;
        height: 50px;
        z-index: 20;

        .no-style-msg {
          color: #333333;

          .search-text,
          .search-btn {
            position: absolute;
            outline: none;
            top: 0;
            border: 1px solid #e0e0e0;
            transition: all .2s;
          }

          .search-text {
            right: 51px;
            //left: 0;
            z-index: 1;
            width: 244px;
            height: 50px;
            padding: 0 10px;
            font-size: 14px;
            line-height: 50px;
          }

          .search-btn {
            right: 0;
            z-index: 2;
            width: 52px;
            height: 50px;
            font-size: 24px;
            line-height: 24px;
            background: white;
            font-weight: 600;
            color: #616161;

            &:hover {
              color: white;
              background-color: #ff6700;
            }
          }
        }

        .search-hot-words {
          position: absolute;
          top: 14px;
          right: 62px;
          z-index: 2;
          text-align: right;
          transition: opacity .2s;
        }

        .keyword-list {
          position: absolute;
          left: 1px;
          top: 50px;
          z-index: 20;
          width: 244px;
          box-sizing: border-box;
          border: 1px solid #ff6700;
          border-top: 0;
          background: white;

          .result-list {
            margin: 0;
            padding: 0;
            list-style-type: none;
            display: block;

            li {
              display: list-item;

              a {
                position: relative;
                display: block;
                padding: 6px 15px;
                font-size: 12px;
                color: #424242;
              }
            }
          }
        }
      }
    }
  }

  .sub-menu {
    //display: none;
    height: 0;
    position: absolute;
    top: 100px;
    z-index: 24;
    width: 100%;
    //border-top: 1px solid #e0e0e0;
    background: white;
    overflow: hidden;

    .container {
      position: relative;
      width: 1226px;
      margin: 0 auto;

      .children-list {
        margin: 0;
        padding: 0;
        list-style-type: none;
        font-size: 12px;
        display: block;
        margin-block-start: 1em;
        margin-block-end: 1em;
        margin-inline-start: 0;
        margin-inline-end: 0;
        padding-inline-start: 40px;

        // 第一种写法
        //>li:not(:first-child):before {
        // 第二种写法  匹配到div的父元素的第2个及之后的子元素，不论元素的类型
        //>li:nth-child(n+2):before{
        // 第三种写法
        //li:nth-of-type(n+2):before{
        // 第四种写法
        li + li:before {
          position: absolute;
          left: 0;
          top: 35px;
          z-index: 1;
          width: 1px;
          height: 100px;
          content: "";
          background-color: #e0e0e0;
        }

        li {
          position: relative;
          float: left;
          width: 180px;
          padding: 35px 12px 0;
          text-align: center;
          display: list-item;

          a {
            color: #757575;

            .figure {
              width: 160px;
              height: 110px;
              margin: 0 auto 16px;
              text-align: center;

              img {
                width: 160px;
                height: 110px;
                border: 0;
              }
            }

            .title {
              color: #333333;
              margin: 0;
              line-height: 20px;
            }

            .price {
              margin: 0;
              line-height: 20px;
              color: #ff6700;
            }
          }
        }
      }
    }
  }

  .slide-down {
    display: block;
    height: 229px;
  }

  .header-nav-menu-active {
    box-shadow: 0 3px 4px rgba(0, 0, 0, .18) !important;
    transition: box-shadow .2s ease 0s, height 0.3s ease 0s, -webkit-box-shadow .2s ease 0s;
  }

  .orange-border {
    border: 1px solid #ff6700 !important;
  }

}
</style>
