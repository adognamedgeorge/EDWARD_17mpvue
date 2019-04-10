<template>
  <div @click="clickHandle">
    <div class="userinfo" @click="bindViewTap">
      <img class="userinfo-avatar" src="/static/images/title.jpg" />

      <div class="userinfo-nickname">
        <card :nick="userInfo.nickName" :tel="userInfo.tel" :add="userInfo.address"></card>
      </div>
    </div>

    <div class="divAds">
      <img class="horn" src="/static/images/ads.png" alt="horn">
      <ul>
        <li>劳动节特惠！全场7折！数量有限！先到先得！</li>
      </ul>
    </div>
    <!--搜索框-->
    <search></search>
    <category></category>
    <!--<form class="form-container">-->
      <!--<input type="text" class="form-control" :value="motto" placeholder="v-model" />-->
      <!--<input type="text" class="form-control" v-model="motto" placeholder="v-model" />-->
      <!--<input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy" />-->
    <!--</form>-->
    <a href="/pages/counter/main" class="counter">去往Vuex示例页面</a>
    <div class="all">
        <div class="left">
        </div>
        <div class="right">
        </div>
    </div>
  </div>
</template>

<script>
import card from '@/components/card'
import search from '@/components/search'
import category from '@/components/category/category'

export default {
  data () {
    return {
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: '杭州格燃食品有限公司',
        tel: '12345678900',
        address: '浙江省杭州市西湖区文三路199号',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },

  components: {
    card,
    search,
    category
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped lang="scss">
.userinfo {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin: rpx(50);
}

.userinfo-avatar {
  width: rpx(200);
  height: rpx(200);
  border-radius: 10%;
  margin-right: rpx(40);
}

.userinfo-nickname {
  color: #aaa;
  flex: 1;
}

.divAds {
  color: #ff0000;
  font-size: .3rem;
  display: flex;
  vertical-align: center;
  flex-direction: row;
  justify-content: center;
  .horn {
    width: rpx(40);
    height: rpx(40);
    padding-right: rpx(15);
  }
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all{
  width:7.5rem;
  height:1rem;
  background-color:blue;
}
.all:after{
  display:block;
  content:'';
  clear:both;
}
.left{
  float:left;
  width:3rem;
  height:1rem;
  background-color:red;
}

.right{
  float:left;
  width:4.5rem;
  height:1rem;
  background-color:green;
}
</style>
