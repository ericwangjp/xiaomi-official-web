<template>
  <div class="goods-item-container">
    <a :href="goodsInfo.targetUrl">
      <div class="figure">
        <img :src="goodsInfo.imageUrl" alt="">
      </div>
      <h3 class="title">{{ goodsInfo.goodsTitle }}</h3>
      <p class="desc">{{ goodsInfo.goodsDesc }}</p>
      <p class="price" v-if="goodsInfo.type === 1">
        <span class="num">{{ goodsInfo.goodsPrice }}元起</span>
      </p>
      <p class="discount" v-else>
        <span class="new">{{ goodsInfo.goodsPrice }}元</span>
        <del>{{ goodsInfo.oldPrice }}元</del>
      </p>
    </a>
  </div>
</template>

<script>
export default {
  name: "GoodsItem",
  props: ["goodsInfo"]
}
</script>

<style scoped lang="less">
.goods-item-container {
  height: 300px;
  width: 234px;

  a {
    display: block;
    height: 100%;
    box-sizing: border-box;
    padding: 20px 0;

    .figure {
      width: 160px;
      height: 160px;
      margin: 0 auto 18px;

      img {
        border: 0;
        width: 160px;
        height: 160px;
      }
    }

    .title {
      margin: 0 10px 2px;
      text-align: center;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
      font-size: 14px;
      font-weight: 400;
      color: #333333;
    }

    .desc {
      margin: 0 10px 10px;
      height: 18px;
      line-height: 18px;
      font-size: 12px;
      color: #b0b0b0;
      text-align: center;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
    }

    .price,
    .discount {
      margin: 0 10px 14px;
      text-align: center;
      color: #ff6700;
      font-size: 14px;
    }

    .discount {
      del {
        margin-left: 0.5em;
        color: #b0b0b0;
      }
    }
  }
}
</style>
