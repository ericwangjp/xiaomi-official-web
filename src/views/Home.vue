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
          </div>
        </div>
      </el-main>
      <el-footer height="60px">Footer</el-footer>
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

export default {
  name: 'Home',
  components: {
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

    .el-footer {
      padding: 0;
      margin: 0;
    }
  }
}

</style>
