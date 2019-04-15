<template>
  <div id="divList">
    <ul>
      <li v-for="(item, index) of listData" :key="index">
        <div class="liWrap">
          <div class="liHead">
            <div class="headLf">
              <img :src="item.url" alt="">
            </div>
            <div class="headRt">
              <p>{{item.text}}</p>
              <div>
                <span>
                  ¥{{item.price}}/{{item.unit}}
                </span>
                <img src="/static/images/arrow_down.png" alt="">
              </div>
            </div>
          </div>
          <div class="liFoot">
            <div class="diVal">
              <a href="javascript:;">-</a>
              <input type="text" value="5">
              <a href="javascript:;">+</a>
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
  name: 'categoryList',
  data () {
    return {
      listData: []
    }
  },
  methods: {
    getList () {
      let Fly = require('flyio')
      let fly = new Fly()
      fly.get('https://easy-mock.com/mock/5ca466b55eeed03805bf4949/edward/edward')
        .then((res) => {
          this.listData = res.data['data']
          console.log(res)
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  mounted () {
    this.getList()
  }
}
</script>

<style scoped lang="scss">
#divList {
  height: rpx(1200);
  overflow-y: scroll;
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
          overflow: hidden;
          max-height: rpx(100);
          line-height: rpx(50);
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
        display: flex;
        flex-direction: row;
        a {
          width: rpx(80);
        }
        a:first-child {
          border-right: none;
        }
        a:last-child {
          border-left: none;
        }
        input {
          width: rpx(100);
        }
        a, input {
          text-align: center;
          height: rpx(80);
          line-height: rpx(80);
          border: 1px solid grey;
        }
      }
      button {
        flex: 1;
        float: right;
        height: rpx(80);
        line-height: rpx(80);
        margin-left: rpx(20);
        background-color: red;
        text-align: center;
        color: #ffffff;
        font-size: rpx(30);
      }
    }
  }
}
</style>
