<template>
  <div class="pic-square-container">
    <ul>
      <li v-for="item in picItemList" :key="item.imgUrl">
        <a :href="item.targetUrl">
          <img :src="item.imgUrl" alt="">
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "PicItem",
  props: ['picItemList']
}
</script>

<style scoped lang="less">
.pic-square-container {
  width: 234px;
  float: left;
  margin-left: 14px;
  max-height: 1px;

  ul {
    margin: 0 0 -14px -14px;
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

      a {
        display: block;
        width: 100%;
        height: 100%;
        color: #757575;

        img {
          height: 300px;
          width: 234px;
          border: 0;
        }
      }
    }
  }
}
</style>
