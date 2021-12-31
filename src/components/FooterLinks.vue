<template>
  <div class="foot-links-container clearfix">
    <dl class="col-links col-links-first" v-for="item in dataList" :key="item.title">
      <dt>{{ item.title }}</dt>
      <dd v-for="childItem in item.child" :key="childItem.subTitle">
        <a :href="childItem.targetUrl">{{ childItem.subTitle }}</a>
      </dd>
    </dl>
    <div class="col-contact">
      <p class="phone">400-100-5678</p>
      <p>8:00-18:00（仅收市话费）</p>
      <el-button type="danger" icon="el-icon-s-comment" size="mini" plain>人工客服</el-button>
      <div class="follow">
        关注小米:
        <a href="https://weibo.com/xiaomishangcheng" target="_blank" class="wb"></a>
        <a href="javascript:void(0);" target="_blank" class="wx" @mouseenter="enter" @mouseleave="leave"></a>
        <img src="https://cdn.cnbj1.fds.api.mi-img.com/staticsfile/global/wx-img.png" alt="" :class="{active:active}">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterLinks",
  data() {
    return {
      dataList: [
        {
          title: '帮助中心',
          child: [
            {
              targetUrl: "https://www.mi.com/service/account/Account%20registration",
              subTitle: "账户管理"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "购物指南"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "订单操作"
            }
          ]
        }, {
          title: '服务支持',
          child: [
            {
              targetUrl: "https://www.mi.com/service/account/Account%20registration",
              subTitle: "售后政策"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "自助服务"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "相关下载"
            }
          ]
        }, {
          title: '线下门店',
          child: [
            {
              targetUrl: "https://www.mi.com/service/account/Account%20registration",
              subTitle: "小米之家"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "服务网点"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "授权体验店/专区"
            }
          ]
        }, {
          title: '关于小米',
          child: [
            {
              targetUrl: "https://www.mi.com/service/account/Account%20registration",
              subTitle: "了解小米"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "加入小米"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "投资者关系"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "企业社会责任"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "廉洁举报"
            }
          ]
        }, {
          title: '关注我们',
          child: [
            {
              targetUrl: "https://www.mi.com/service/account/Account%20registration",
              subTitle: "新浪微博"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "官方微信"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "联系我们"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "公益基金会"
            }
          ]
        }, {
          title: '特色服务',
          child: [
            {
              targetUrl: "https://www.mi.com/service/account/Account%20registration",
              subTitle: "F码通道"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "礼物码"
            }, {
              targetUrl: "https://www.mi.com/service/buy/SalesTime",
              subTitle: "防伪查询"
            }
          ]
        }
      ],
      active: false
    }
  },
  methods: {
    enter() {
      this.active = true;
    },
    leave() {
      this.active = false;
    }
  }
}
</script>

<style scoped lang="less">
.foot-links-container {
  padding: 40px 0;
  width: 1226px;
  margin: 0 auto;

  .col-links {
    float: left;
    width: 160px;
    margin: 0;

    dt {
      margin: -1px 0 26px;
      font-size: 14px;
      line-height: 1.25;
      color: #424242;
    }

    dd {
      margin: 10px 0 0;
      font-size: 12px;

      a {
        color: #757575;

        &:hover {
          color: #ff6700;
        }
      }


    }
  }

  .col-contact {
    float: right;
    width: 251px;
    border-left: 1px solid #e0e0e0;
    text-align: center;
    color: #616161;

    .phone {
      font-size: 22px;
      line-height: 1;
      color: #ff6700;
    }

    p {
      margin: 0 0 5px 0;
      font-size: 12px;
    }

    .follow {
      font-size: 12px;
      margin-top: 10px;
      position: relative;

      .wb {
        background: url("https://cdn.cnbj1.fds.api.mi-img.com/staticsfile/global/wb.png") 50% 0 no-repeat;
        background-size: cover;

        &:hover {
          background-image: url("https://cdn.cnbj1.fds.api.mi-img.com/staticsfile/global/wb@2x.png")
        }
      }

      .wx {
        background: url("https://cdn.cnbj1.fds.api.mi-img.com/staticsfile/global/wx.png") 50% 0 no-repeat;
        background-size: cover;

        &:hover {
          background-image: url("https://cdn.cnbj1.fds.api.mi-img.com/staticsfile/global/wx@2x.png");
        }
      }

      a {
        width: 24px;
        height: 24px;
        display: inline-block;
        vertical-align: middle;
        margin-left: 6px;
        margin-top: -3px;

      }

      img {
        width: 126px;
        height: 126px;
        z-index: 2;
        position: absolute;
        top: 20px;
        left: 100px;
        display: none;
        border: 0;
      }

      .active {
        display: block;
      }
    }
  }
}
</style>
