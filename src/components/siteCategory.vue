<style lang="scss" scoped>
@import '../assets/_all.scss';
  .site-category {
    position: absolute;
    left: 0;
    top: 0;
    z-index: 5;
    width: 234px;
    height: 460px;
    font-size: 14px;
  }
  .category-list {
    height: 460px;
    background-color: rgba(0,0,0,0.5);
    padding: 20px 0;
  }
  .category-item {
    color: #fff;
    text-align: left;
    height: 42px;
    text-indent: 30px;
    line-height: 42px;
    &:hover {
      background-color: $米橘;
    }
    position: relative;
  }
  .category-item i{
    position: absolute;
    right: 20px;
    font-size: 0.8em;
    top: 13px;
    opacity: 0.6;
  }
</style>

<template>
  <div class="site-category">
    <ul class="category-list">
      <li class="category-item" v-for="item of cdata">
        {{item.title}}
        <a :href="item.href"></a>
        <i class="iconfont">&#xe601;</i>
      </li>
    </ul>
    
  </div>
</template>

<script>
export default {
  props: ['cdata']
}
</script>
