<template>
  <div class="foot-header-container clearfix">
    <ul class="list-service clearfix">
      <li v-for="item in serviceList" :key="item.title">
        <a :href="item.targetUrl">
          <em class="iconfont" :class="item.iconClass"></em>
          {{ item.title }}
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "FootHeader",
  data() {
    return {
      serviceList: [
        {
          title: "预约维修服务",
          iconClass: "icon-alipay-tool-hardware",
          targetUrl: "https://www.mi.com/service/quick-repair"
        }, {
          title: "7天无理由退货",
          iconClass: "icon-alipay-icon-test1",
          targetUrl: "https://www.mi.com/service/exchange#back"
        }, {
          title: "15天免费换货",
          iconClass: "icon-alipay-record",
          targetUrl: "https://www.mi.com/service/exchange#back"
        }, {
          title: "满69包邮",
          iconClass: "icon-alipay-gift",
          targetUrl: "https://www.mi.com/service/buy/Postal%20policy"
        }, {
          title: "520余家售后网点",
          iconClass: "icon-alipay-map",
          targetUrl: "https://www.mi.com/service/sitelist"
        }
      ]
    }
  }
}
</script>

<style scoped lang="less">
.foot-header-container {
  padding: 27px 0;
  border-bottom: 1px solid #e0e0e0;
  width: 1226px;
  margin: 0 auto;

  .list-service {
    margin: 0;
    padding: 0;
    list-style-type: none;

    li {
      float: left;
      width: 19.8%;
      height: 25px;
      font-size: 16px;
      border-left: 1px solid #e0e0e0;
      line-height: 25px;
      text-align: center;

      &:first-child {
        border-left: 0;
      }

      a {
        color: #616161;
        transition: color .2s;

        em {
          margin-right: 6px;
          font-size: 24px;
          line-height: 24px;
          vertical-align: -4px;
        }

        &:hover {
          color: #ff6700;
        }
      }
    }
  }
}
</style>
