<template>
  <div class="phone-header">
    <a href="https://www.mi.com/redmik40">
      <img
          src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/f334fbd05d5681bb838fefd1c815d88c.jpg?thumb=1&w=2452&h=240&f=webp&q=90"
          alt="">
    </a>
  </div>
</template>

<script>
export default {
  name: "PhoneHeader"
}
</script>

<style scoped lang="less">
.phone-header {
  height: 120px;
  margin: 22px 0;
  overflow: hidden;

  a {
    color: #757575;

    img {
      border: 0;
      width: 1226px;
      height: 120px;
      aspect-ratio: auto 1226/120;
    }
  }
}
</style>
