<template>
  <div id="divList">
    <ul>
      <li v-for="(item, index) of sortsList" :key="index">{{item.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'categorySorts',
  data () {
    return {
      sortsList: []
    }
  },
  methods: {
    getSorts () {
      let Fly = require('flyio')
      let fly = new Fly()
      fly.get('https://easy-mock.com/mock/5c9edbfc8aaa6f3254a8831a/yunmayi/getTopCat')
        .then((res) => {
          this.sortsList = res.data['data']
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  mounted () {
    this.getSorts()
  }
}
</script>

<style scoped lang="scss">
#divList {
  ul {
    li {
      height: rpx(90);
      text-align: center;
      line-height: rpx(90);
      font-size: .3rem;
      background-color: #f5f5f5;
    }
    li:first-child {
      background-color: inherit;
    }
  }
}
</style>
