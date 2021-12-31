<template>
  <div class="home-electric-container">
    <div class="box-head clearfix">
      <h2>家电</h2>
      <!--      <div class="more">-->
      <more-tabs :tab-data="tabsData"/>
      <!--      </div>-->
    </div>

    <div class="box-body">
      <div class="row">
        <pic-item :pic-item-list="electricList"/>
        <div class="span16">
          <div class="goods-list">
            <ul>
              <li v-for="(item,index) in goodsList" :key="index">
                <goods-item :goods-info="item"/>
              </li>
              <li class="small-item">
                <small-goods-item/>
              </li>
              <li class="small-item">
                <scan-more/>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import PicItem from "@/components/PicItem";
import MoreTabs from "@/components/MoreTabs";
import GoodsItem from "@/components/GoodsItem";
import SmallGoodsItem from "@/components/SmallGoodsItem";
import ScanMore from "@/components/ScanMore";

export default {
  name: "HomeElectric",
  components: {ScanMore, SmallGoodsItem, GoodsItem, MoreTabs, PicItem},
  data() {
    return {
      electricList: [
        {
          targetUrl: 'https://www.mi.com/buy/detail?product_id=10000316',
          imgUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/3d47879ec183e25a36e67e0219636e60.jpg?thumb=1&w=468&h=600&f=webp&q=90'
        }, {
          targetUrl: 'https://www.mi.com/buy/detail?product_id=14781',
          imgUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/ca83e0294e7d725690b0576a1a4681e2.jpg?thumb=1&w=468&h=600&f=webp&q=90'
        }
      ],
      tabsData: ["热门", "电视影音"],
      goodsList: [
        {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14779",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/82ff5ea76730fdf6f91aba5d3b2e5739.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米电视6 65”  OLED',
          goodsDesc: '小米电视6 65″OLED',
          goodsPrice: '6999',
          type: 1
        }, {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14438",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/c7c15101f2c8a652a4a0d069501d1e53.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米电视6 至尊版 65英寸',
          goodsDesc: '画质新境界',
          goodsPrice: '7999',
          type: 1
        }, {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14779",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/82ff5ea76730fdf6f91aba5d3b2e5739.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米电视6 65”  OLED',
          goodsDesc: '小米电视6 65″OLED',
          goodsPrice: '6999',
          type: 1
        }, {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14438",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/c7c15101f2c8a652a4a0d069501d1e53.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米电视6 至尊版 65英寸',
          goodsDesc: '画质新境界',
          goodsPrice: '7999',
          type: 1
        }, {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14779",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/82ff5ea76730fdf6f91aba5d3b2e5739.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米电视6 65”  OLED',
          goodsDesc: '小米电视6 65″OLED',
          goodsPrice: '6999',
          type: 1
        }, {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14438",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/c7c15101f2c8a652a4a0d069501d1e53.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米电视6 至尊版 65英寸',
          goodsDesc: '画质新境界',
          goodsPrice: '7999',
          type: 1
        }, {
          targetUrl: "https://www.mi.com/buy/detail?product_id=14779",
          imageUrl: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/82ff5ea76730fdf6f91aba5d3b2e5739.jpg?thumb=1&w=400&h=400&f=webp&q=90',
          goodsTitle: '小米电视6 65”  OLED',
          goodsDesc: '小米电视6 65″OLED',
          goodsPrice: '6999',
          type: 1
        }
      ]
    }
  }
}
</script>

<style scoped lang="less">
.home-electric-container {
  margin-bottom: 8px;

  .box-head {
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
  }

  .box-body {
    .row {
      margin-left: -14px;

      .span16 {
        width: 978px;
        float: left;
        margin-left: 14px;
        min-height: 1px;

        .goods-list {
          ul {
            margin: 0 0 -14px -14px;
            width: 992px;
            height: 614px;
            padding: 0;

            li {
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

            .small-item {
              height: 93px;
              padding-top: 50px;
              position: relative;
              z-index: 1;
              float: left;
              width: 234px;
              margin-left: 14px;
              margin-bottom: 14px;
              background: white;
              transition: all .2s linear;
            }
          }
        }
      }
    }
  }
}
</style>
