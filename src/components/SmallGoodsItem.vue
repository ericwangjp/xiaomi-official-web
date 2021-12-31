<template>
  <div class="small-goods-container">
    <a :href="targetUrl">
      <div class="goods-img">
        <img :src="imgUrl" alt="">
      </div>
      <h3 class="title">{{ title }}</h3>
      <p class="price">
        <span>{{ price }}</span>元
      </p>
    </a>
  </div>
</template>

<script>
export default {
  name: "SmallGoodsItem",
  props: {
    targetUrl: String,
    imgUrl: {
      type: String,
      default() {
        return "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/1612c93ad4756215774a0dbec7a81bb2.jpg?thumb=1&w=200&h=200&f=webp&q=90"
      }
    },
    title: {
      type: String,
      // required: true,
      default() {
        return "米家电烤箱"
      }
    },
    price: {
      type: String,
      default() {
        return "299"
      }
    },
  }
}
</script>

<style scoped lang="less">
.small-goods-container {
  a {
    color: #757575;

    .goods-img {
      position: absolute;
      right: 20px;
      top: 32px;
      width: 80px;
      height: 80px;

      img {
        width: 80px;
        height: 80px;
      }
    }

    .title {
      color: #333333;
      margin: -10px 110px 5px 30px;
      font-size: 14px;
      font-weight: 400;
    }

    .price {
      margin: 0 110px 0 30px;
      font-size: 12px;
      color: #ff6700;

      span {
        font-size: 14px;
      }
    }
  }
}
</style>
