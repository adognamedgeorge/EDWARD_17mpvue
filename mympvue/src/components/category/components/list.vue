<template>
  <div id="divList">
    <ul>
      <li>
        <div class="liWrap">
          <div class="liHead">
            <div class="headLf">
              <img src="/static/images/title.jpg" alt="">
            </div>
            <div class="headRt">
              <p>新包装江小白40度80 ml*48瓶</p>
              <div>
                <span>
                  ¥585/箱
                </span>
                <img src="/static/images/arrow_down.png" alt="">
              </div>
            </div>
          </div>
          <div class="liFoot">
            <div class="diVal">
              <a href="">-</a>
              <input type="text" value="5">
              <a href="">+</a>
            </div>
            <button>加入购物车</button>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'categoryList'
}
</script>

<style scoped lang="scss">
#divList {
  .liWrap {
    display: flex;
    flex-direction: column;
    padding: rpx(20) rpx(20) rpx(20) 0;
    margin-left: rpx(20);
    border-bottom: 1px solid #f5f5f5;
    .liHead {
      display: flex;
      flex-direction: row;
      margin-bottom: rpx(20);
      .headLf {
        width: rpx(150);
        height: rpx(150);
        margin-right: rpx(25);
        img {
          width: 100%;
          height: 100%;
        }
      }
      .headRt {
          flex: 1;
        p {
          font-size: rpx(30);
        }
        div {
          position: relative;
          span {
            font-size: rpx(28);
            color: red;
          }
          img {
            display: inline-block;
            width: rpx(36);
            height: rpx(36);
            position: absolute;
            bottom: 0;
          }
        }
      }
    }
    .liFoot {
      display: flex;
      flex-direction: row;
      .diVal {
        width: rpx(240);
        height: rpx(80);
        background-color: red;
        display: flex;
        flex-direction: row;
        a {
          width: rpx(80);
          height: rpx(80);
          background: yellow;
        }
        input {
          width: 50px;
        }
      }
      button {
        flex: 1;
        float: right;
      }
    }
  }
}
</style>
