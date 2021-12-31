<template>
  <div class="site-info-container">
    <div class="site-info clearfix">
      <div class="logo">小米官网</div>
      <div class="info-text">
        <p class="sites">
          <template v-for="(item,index) in siteList">
            <a :href="item.targetUrl" target="_blank" :key="item.name">{{ item.name }}</a>
            <span class="sep" :key="index" v-if="!(index===siteList.length-1)">|</span>
          </template>
        </p>
        <p class="sites">
          <template v-for="(item,index) in thirdSites">
            <a :href="item.targetUrl" target="_blank" :key="item.name">{{ item.name }}</a>
            <span class="sep" :key="index" v-if="!(index===thirdSites.length-1)">|</span>
          </template>
        </p>
        <p>
          <template v-for="item in recordList">
            <a :href="item.targetUrl" target="_blank" :key="item.name">{{ item.name }}</a>
          </template>
        </p>
      </div>
      <div class="info-links">
        <a :href="item.targetUrl" target="_blank" v-for="(item,index) in infoLinkList" :key="index">
          <img :src="item.imgUrl" :alt="item.name">
        </a>
      </div>
    </div>
    <div class="slogan">探索黑科技，小米为发烧而生</div>
  </div>
</template>

<script>
export default {
  name: "FooterSiteInfo",
  data() {
    return {
      siteList: [
        {name: "小米商城", targetUrl: "https://www.mi.com/index.html"},
        {name: "MIUI", targetUrl: "https://www.mi.com/index.html"},
        {name: "米家", targetUrl: "https://www.mi.com/index.html"},
        {name: "米聊", targetUrl: "https://www.mi.com/index.html"},
        {name: "多看", targetUrl: "https://www.mi.com/index.html"},
        {name: "游戏", targetUrl: "https://www.mi.com/index.html"},
        {name: "政企服务", targetUrl: "https://www.mi.com/index.html"},
        {name: "小米天猫店", targetUrl: "https://www.mi.com/index.html"},
        {name: "小米集团隐私政策", targetUrl: "https://www.mi.com/index.html"},
        {name: "小米公司儿童信息保护规则", targetUrl: "https://www.mi.com/index.html"},
        {name: "小米商城隐私政策", targetUrl: "https://www.mi.com/index.html"},
        {name: "小米商城用户协议", targetUrl: "https://www.mi.com/index.html"},
        {name: "问题反馈", targetUrl: "https://www.mi.com/index.html"},
        {name: "Select Location", targetUrl: "https://www.mi.com/index.html"},
      ],
      thirdSites: [
        {name: "北京互联网法院法律服务工作站", targetUrl: "http://www.mi.com/beihu"},
        {name: "中国消费者协会", targetUrl: "http://www.mi.com/beihu"},
        {name: "北京市消费者协会", targetUrl: "http://www.mi.com/beihu"},
      ],
      recordList: [
        {name: "©mi.com", targetUrl: "http://beian.miit.gov.cn/"},
        {name: "京ICP证110507号", targetUrl: "http://beian.miit.gov.cn/"},
        {name: "京ICP备10046444号", targetUrl: "http://beian.miit.gov.cn/"},
        {
          name: "京公网安备11010802020134号",
          targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"
        },
        {
          name: "京网文[2020]0276-042号",
          targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"
        },
        {
          name: "（京）网械平台备字（2018）第00005号",
          targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"
        },
        {
          name: "互联网药品信息服务资格证 (京)-非经营性-2014-0090",
          targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"
        },
        {name: "营业执照", targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"},
        {name: "医疗器械质量公告", targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"},
        {name: "增值电信业务许可证", targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"},
        {
          name: " 网络食品经营备案 京食药网食备202010048 ",
          targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"
        },
        {name: "食品经营许可证", targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"},
        {
          name: " 违法和不良信息举报电话：171-5104-4404 ",
          targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"
        },
        {name: "知识产权侵权投诉", targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"},
        {
          name: " 本网站所列数据，除特殊说明，所有数据均出自我司实验室测试 ",
          targetUrl: "http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134"
        },
      ],
      infoLinkList: [
        {
          name: "TRUSTe Privacy Certification",
          targetUrl: "https://privacy.truste.com/privacy-seal/validation?rid=4fc28a8c-6822-4980-9c4b-9fdc69b94eb8&lang=zh-cn",
          imgUrl: "https://i1.mifile.cn/f/i/17/site/truste.png"
        }, {
          name: "诚信网站",
          targetUrl: "https://credit.cecdc.com/CX20120926001783002010.html",
          imgUrl: "https://s01.mifile.cn/i/v-logo-2.png"
        }, {
          name: "可信网站",
          targetUrl: "https://xyt.xinchacha.com/pcinfo?sn=523009637759455232&certType=6",
          imgUrl: "https://xyt.xinchacha.com/img/icon/icon3.png"
        }, {
          name: "诚信经营 放心消费",
          targetUrl: "https://www.mi.com/service/buy/commitment",
          imgUrl: "https://i8.mifile.cn/b2c-mimall-media/ba10428a4f9495ac310fd0b5e0cf8370.png"
        }, {
          name: "诚信经营 放心消费",
          targetUrl: "https://webcert.cnmstl.net/cert/grade?sn=3af21034e35011eab3ea00163e068ceb",
          imgUrl: "https://cnbj1.fds.api.xiaomi.com/b2c-misite-activity/f1ee261b96ae71e845efba398efeca02.png"
          //  https://cnbj1.fds.api.xiaomi.com/b2c-misite-activity/8f13fcd1fc3ceee428c96e71976dbafa.png
        },
      ]
    }
  }
}
</script>

<style scoped lang="less">
.site-info-container {
  padding: 30px 0;
  font-size: 12px;
  background: #fafafa;

  .site-info {
    position: relative;
    width: 1226px;
    margin: 0 auto;

    .logo {
      width: 56px;
      height: 56px;
      margin-right: 20px;
      background: url("https://s02.mifile.cn/assets/static/image/logo-mi2.png") no-repeat;
      background-size: 56px;
      position: absolute;
      top: 0;
      left: 0;
      text-align: left;
      text-indent: -9999em;
      overflow: hidden;
    }

    .info-text {
      color: #b0b0b0;
      padding-left: 77px;

      p {
        a {
          color: #b0b0b0;

          &:hover {
            color: #ff6700;
          }
        }
      }

      .sites {
        margin: 0;
        line-height: 18px;

        a {
          color: #757575;
        }

        .sep {
          margin: 0 0.25em;
        }
      }
    }

    .info-links {
      height: 28px;
      margin: 4px 0 15px;
      padding-left: 77px;

      a {
        display: inline-block;
        color: #757575;

        img {
          width: auto;
          height: 28px;
          margin-left: 0;
          border: 0;
        }
      }
    }
  }

  .slogan {
    clear: both;
    margin: 30px auto 0;
    width: 100%;
    height: 19px;
    background: url("https://cdn.cnbj1.fds.api.mi-img.com/staticsfile/global/slogan2020.png") no-repeat center 0;
    display: block;
    text-align: left;
    text-indent: -9999em;
    overflow: hidden;
  }
}
</style>
