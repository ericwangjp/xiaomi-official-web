<template>
  <div class="smart-wear-container">
    <div class="box-header clearfix">
      <h2 class="title">智能穿戴</h2>
      <div class="more">
        <ul>
          <li v-for="(item,index) in tabs" :key="item" @mouseenter="enter(index)" :class="{active:curIndex === index}">
            {{ item }}
          </li>
        </ul>
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
            <!--使用is 时当前标签会被组件的标签完全替换-->
            <!--            <li class="phone-list-item" is="scan-more" v-bind="childInfo">-->
            <!--              &lt;!&ndash;              <scan-more v-bind="childInfo"/>&ndash;&gt;-->
            <!--            </li>-->
            <li class="phone-list-item">
              <scan-more v-bind="childInfo"/>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ScanMore from "@/components/ScanMore";
import GoodsItem from "@/components/GoodsItem";

export default {
  name: "SmartWear",
  components: {GoodsItem, ScanMore},
  data() {
    return {
      tabs: ["热门", "穿戴"],
      goodsList: [
        {
          targetUrl: "https://www.mi.com/shouhuan6/nfc",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/b28153b80cb2c67564608e56d5c2f3f3.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米手环6 NFC版',
          goodsDesc: '全屏实力',
          goodsPrice: '249',
          oldPrice: '279'
        }, {
          targetUrl: "https://www.mi.com/redmi-watch-mulan",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/cfec307342eb35ee4a437f664004c50f.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Redmi 手表',
          goodsDesc: '35g超轻/1.4"大屏/多功能NFC/7天长续航',
          goodsPrice: '269',
          oldPrice: '299'
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/0cc4e8e58d7288cd8dff13b98bdc3ea8.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Xiaomi 真无线降噪耳机 3 Pro',
          goodsDesc: '动态降噪 静听曼妙',
          goodsPrice: '689',
          oldPrice: '699'
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/0cc4e8e58d7288cd8dff13b98bdc3ea8.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Xiaomi 真无线降噪耳机 3 Pro',
          goodsDesc: '动态降噪 静听曼妙',
          goodsPrice: '689',
          oldPrice: '699'
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/0cc4e8e58d7288cd8dff13b98bdc3ea8.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Xiaomi 真无线降噪耳机 3 Pro',
          goodsDesc: '动态降噪 静听曼妙',
          goodsPrice: '689',
          oldPrice: '699'
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/0cc4e8e58d7288cd8dff13b98bdc3ea8.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Xiaomi 真无线降噪耳机 3 Pro',
          goodsDesc: '动态降噪 静听曼妙',
          goodsPrice: '689',
          oldPrice: '699'
        }, {
          targetUrl: "https://www.mi.com/redminote11",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/0cc4e8e58d7288cd8dff13b98bdc3ea8.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: 'Xiaomi 真无线降噪耳机 3 Pro',
          goodsDesc: '动态降噪 静听曼妙',
          goodsPrice: '689',
          oldPrice: '699'
        }
      ],
      childInfo: {
        targetUrl: "https://www.mi.com/search?keyword=%E6%89%8B%E8%A1%A8%E6%89%8B%E7%8E%AF",
      },
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
.smart-wear-container {
  margin-bottom: 8px;

  .box-header {
    position: relative;
    height: 58px;
    -webkit-font-smoothing: antialiased;

    .title {
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

      ul {
        margin: 0;
        padding: 16px 0 0;
        font-size: 16px;

        li {
          margin: 0 0 0 30px;
          padding: 2px 0;
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

          > li:last-child {
            padding-top: 50px;
            height: 93px;
          }

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

          }
        }
      }
    }
  }

}
</style>
