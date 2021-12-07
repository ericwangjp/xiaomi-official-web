<template>
  <div class="container">
    <div class="slide-container">
      <ul class="category-list clearfix">
        <li class="category-item" v-for="(item,index) in categories" :key="index" @mouseenter="enter(index)"
            @mouseleave="isShow=false" :class="{'category-item-active':isShow&&curIndex===index}">
          <a href="javascript:;" class="category-title">
            {{ item }}
            <em class="right-arrow iconfont icon-alipay-arrow-right"></em>
          </a>
          <div class="children clearfix">
            <ul class="children-list">
              <li v-for="(item,index) in childrenList" :key="index">
                <a :href="item.targetUrl">
                  <img :src="item.imageUrl">
                  <span class="goods-title">{{ item.name }}</span>
                </a>
              </li>
            </ul>
            <ul class="children-list">
              <li v-for="(item,index) in childrenList" :key="index">
                <a :href="item.targetUrl">
                  <img :src="item.imageUrl">
                  <span class="goods-title">{{ item.name }}</span>
                </a>
              </li>
            </ul>
            <ul class="children-list">
              <li v-for="(item,index) in childrenList" :key="index">
                <a :href="item.targetUrl">
                  <img :src="item.imageUrl">
                  <span class="goods-title">{{ item.name }}</span>
                </a>
              </li>
            </ul>
            <ul class="children-list">
              <li v-for="(item,index) in childrenList" :key="index">
                <a :href="item.targetUrl">
                  <img :src="item.imageUrl">
                  <span class="goods-title">{{ item.name }}</span>
                </a>
              </li>
            </ul>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "SlideBar",
  data() {
    return {
      categories: ['手机', '电视', '笔记本 平板', '家电', '出行 穿戴', '智能 路由器', '电源 配件', '健康 儿童', '耳机 音响', '生活 箱包'],
      // categories: ['手机'],
      childrenList: [
        {
          name: "Note 11 Pro 系列",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/a95d59ec8c9c6ae7061f314eb4901e7c.png?thumb=1&w=80&h=80&f=webp&q=90",
          targetUrl: "https://www.mi.com/redminote11pro"
        }, {
          name: "Note 11 4G",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e2c570b7cd666114a7d351a1dd10a527.png?thumb=1&w=80&h=80&f=webp&q=90",
          targetUrl: "https://www.mi.com/redminote11-4g"
        }, {
          name: "Note 11 5G",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e2c570b7cd666114a7d351a1dd10a527.png?thumb=1&w=80&h=80&f=webp&q=90",
          targetUrl: "https://www.mi.com/redminote11-4g"
        }, {
          name: "Note 11 4G",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e2c570b7cd666114a7d351a1dd10a527.png?thumb=1&w=80&h=80&f=webp&q=90",
          targetUrl: "https://www.mi.com/redminote11-4g"
        }, {
          name: "Note 11 4G",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e2c570b7cd666114a7d351a1dd10a527.png?thumb=1&w=80&h=80&f=webp&q=90",
          targetUrl: "https://www.mi.com/redminote11-4g"
        }, {
          name: "Note 11 4G",
          imageUrl: "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e2c570b7cd666114a7d351a1dd10a527.png?thumb=1&w=80&h=80&f=webp&q=90",
          targetUrl: "https://www.mi.com/redminote11-4g"
        }
      ],
      isShow: false,
      curIndex: -1
    }
  },
  methods: {
    enter(index) {
      this.isShow = true
      this.curIndex = index
    }
  }
}
</script>

<style scoped lang="less">
.container {
  position: relative;
  width: 1226px;
  margin: 0 auto;

  .slide-container {
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 19;
    width: 234px;
    height: 460px;
    font-size: 14px;

    .category-list {
      height: 420px;
      border: 0;
      color: white;
      background: rgba(105, 101, 101, .6);
      margin: 0;
      padding: 20px 0;
      list-style-type: none;

      .category-item {
        display: list-item;
        text-align: -webkit-match-parent;

        &:hover {
          background-color: #ff6700;
        }

        .category-title {
          color: white;
          position: relative;
          display: block;
          padding-left: 30px;
          height: 42px;
          line-height: 42px;

          .right-arrow {
            position: absolute;
            top: 12px;
            right: 20px;
            font-size: 16px;
            line-height: 16px;
            color: #e0e0e0;
          }
        }

        .children {
          width: 992px;
          display: none;
          position: absolute;
          left: 234px;
          top: 0;
          z-index: 24;
          height: 458px;
          border: 1px solid #e0e0e0;
          border-left: 0;
          background: white;
          box-shadow: 0 8px 16px rgba(0, 0, 0, .18);

          .children-list {
            width: 248px;
            float: left;
            height: 458px;
            margin: 0;
            padding: 2px 0;
            list-style-type: none;
            position: relative;

            li {
              position: relative;
              float: left;
              width: 265px;
              height: 76px;
              display: list-item;
              text-align: -webkit-match-parent;

              a {
                display: block;
                padding: 18px 20px;
                line-height: 40px;
                color: #333333;
                transition: color .2s;
                background-color: rgba(0, 0, 0, 0);

                img {
                  float: left;
                  margin-right: 12px;
                  vertical-align: middle;
                  border: 0;
                  width: 40px;
                  aspect-ratio: auto 40 / 40;
                  height: 40px;
                }

                .goods-title {
                  float: left;
                  width: 172px;
                  line-height: 40px;
                  white-space: nowrap;
                  text-overflow: ellipsis;
                  overflow: hidden;
                }
              }
            }
          }
        }
      }
    }

    .category-item-active {
      .children {
        display: block !important;
      }
    }
  }
}
</style>
