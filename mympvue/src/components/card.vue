<template>
  <div>
    <h3>{{nick}}</h3>
    <p>电话：{{tel}}</p>
    <p>地址：{{add}}</p>
  </div>
</template>

<script>
export default {
  props: [
    'nick',
    'tel',
    'add'
  ]
}
</script>

<style lang="scss" scoped>
div {
  h3 {
    color: #000000;
    padding: rpx(15) 0;
    font-weight: bold;
  }
  p {
    font-size: .3rem;
    padding: rpx(5) 0;
  }
}
</style>
