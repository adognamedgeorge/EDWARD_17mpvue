<template>
  <div class="divSearch">
    <a href="javascript:;" class="searchBtn"></a>
    <input type="text" placeholder="搜索商品" />
    <div class="scanWrap">
      <div class="scanImg">
        <img src="/static/images/icon_scan.png" alt="scan">
      </div>
      <p>扫一扫</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'search'
}
</script>

<style scoped lang="scss">
  .divSearch {
    display: flex;
    flex-direction: row;
    justify-content: center;
    position: relative;
    margin: rpx(30) 0;
    padding: 0 rpx(40) rpx(30);
    border-bottom: rpx(30) solid #f7f7f7;
    .searchBtn {
      position: absolute;
      background: url("../../static/images/icon_search.png") no-repeat;
      left: rpx(60);
      top: rpx(10);
      width: rpx(60);
      height: rpx(60);
      background-size: 100%;
      display: inline-block;
    }
    input {
      display: block;
      padding: 0 rpx(100);
      font-size: .3rem;
      flex: 1;
      background-color: #f7f7f7;
      border-radius: rpx(10);
      height: rpx(80);
      }
  .scanWrap {
    margin-left: rpx(30);
    width: rpx(80);
    display: flex;
    flex-direction: column;
    align-items: center;
    .scanImg {
      width: rpx(60);
      height: rpx(60);
    img {
      width: 100%;
      height: 100%;
          }
        }
    p {
      font-size: rpx(26);
    }
    }
  }
</style>
