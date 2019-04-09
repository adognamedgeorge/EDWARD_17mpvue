<template>
  <div id="divCate">
    <div class="divSorts">
      <category-sorts></category-sorts>
    </div>
    <div class="divList">
      <category-list></category-list>
    </div>
  </div>
</template>

<script>
import categorySorts from './components/sorts'
import categoryList from './components/list'
export default {
  name: 'category',
  components: {
    categorySorts,
    categoryList
  }
}
</script>

<style scoped lang="scss">
#divCate {
  display: flex;
  flex-direction: row;
  .divSorts {
    width: 30%;
  }
  .divList {
    flex: 1;
  }
}
</style>
