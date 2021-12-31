<template>
  <div class="home">
    <el-container>
      <el-header height="40px">
        <top-bar/>
      </el-header>
      <el-main>
        <top-header/>
        <slide-bar/>
        <home-banner/>
        <div class="home-main">
          <div class="container clearfix">
            <phone-header/>
            <mobile-plate/>
            <smart-wear/>
            <home-electric/>
            <home-video/>
          </div>
        </div>
      </el-main>
      <div class="footer clearfix">
        <foot-header/>
        <footer-links/>
        <footer-site-info/>
      </div>
      <home-tool-bar/>
    </el-container>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

import TopBar from "@/components/TopBar";
import TopHeader from "@/components/TopHeader";
import SlideBar from "@/components/SlideBar";
import HomeBanner from "@/components/HomeBanner";
import PhoneHeader from "@/components/PhoneHeader";
import MobilePlate from "@/components/MobilePlate";
import SmartWear from "@/components/SmartWear";
import HomeElectric from "@/components/HomeElectric";
import HomeVideo from "@/components/HomeVideo";
import FootHeader from "@/components/FootHeader";
import FooterLinks from "@/components/FooterLinks";
import FooterSiteInfo from "@/components/FooterSiteInfo";
import HomeToolBar from "@/components/HomeToolBar";

export default {
  name: 'Home',
  components: {
    HomeToolBar,
    FooterSiteInfo,
    FooterLinks,
    FootHeader,
    HomeVideo,
    HomeElectric,
    SmartWear,
    MobilePlate,
    PhoneHeader,
    HomeBanner,
    SlideBar,
    TopHeader,
    TopBar

  }
}
</script>

<style scoped lang="less">
.home {
  .el-container {
    padding: 0;
    margin: 0;

    .el-header {
      padding: 0;
      margin: 0;
    }

    .el-main {
      padding: 0;
      margin: 0;
      //height: 1000px;
      position: relative;

      .home-main {
        padding-top: 4px;
        padding-bottom: 12px;
        background: #f5f5f5;
      }
    }

    .footer {
      width: 100%;
      margin: 0 auto;
    }
  }
}

</style>
