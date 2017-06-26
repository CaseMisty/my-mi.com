<style lang="scss" scoped>
@import '../assets/_all.scss';
  .site-category {
    position: absolute;
    left: 0;
    top: 0;
    z-index: 5;
    height: 460px;
    font-size: 14px;
  }
  .category-list {
    width: 234px;
    height: 460px;
    background-color: rgba(0,0,0,0.5);
    padding: 20px 0;
  }
  .category-item {
    text-align: left;
    height: 42px;
    text-indent: 30px;
    line-height: 42px;
    position: relative;
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
  .category-item a {
    color: #fff;
    width: 100%;
    height: 100%;
    top: 0;
  }
  $category-box-width: 993px;
  $category-box-height: 460px;
  .category-box {
    height: $category-box-height;
    // width: $category-box-width;
    position: absolute;
    left: 234px;
    top: 0;
    background-color: #fff;
    box-shadow: 0 8px 16px rgba(0,0,0,0.18);
    border: 1px solid #e0e0e0;
    box-sizing: border-box;
    z-index: 10;
  }
  .box-list {
    float: left;
    width: $category-box-width/4-1;
    height: $category-box-height;
  }
  .box-item {
    text-align: left;
    height: $category-box-height/6;
    width: 100%;
    line-height: $category-box-height/6;
    position: relative;
    transition: 0.3s;
    &:hover {
      background-color: rgba(0,0,0,0.1);
    }
  }
  .box-item a {
    color: #000;
    transition-duration: 0.3s;
    &:hover {
      color: $米橘;
    }
  }
  .box-item .choose {
    position: absolute;
    right: 10px;
    top: 26px;
    width: 58px;
    height: 22px;
    line-height: 22px;
    border: 1px solid $米橘;
    font-size: 12px;
    color: $米橘;
    transition-duration: 0.3s;
    &:hover{
      cursor: pointer;
      background-color: $米橘;
      color: #fff;
    }
  }
  .item-link {
    display: inline-block;
    line-height: 40px;
    padding: 18px 0 18px 50px;
  }
</style>

<template>
  <div class="site-category">
    <ul class="category-list" @mouseleave="listLeave()">
      <li class="category-item" v-for="(item,index) of cdata" @mouseenter="listHover(index)">
        <a :href="item.href">
          {{item.title}}
          <i class="iconfont">&#xe601;</i>
        </a>
      </li>
    </ul>
    <div class="category-box clearfix" v-show="showBox" @mouseenter="hoverBox=true" @mouseleave="hoverBox=false" :style="boxStyle">
      <ul v-for="list of boxData" class="box-list">
        <li v-for="item of list" class="box-item">
          <a :href="item.href" class="item-link">
            <img src="" alt="">
            {{item.name}}
          </a>
          <a v-if="item.choose" class="choose">选购</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    listHover (index) {
      this.hoverIndex = index
      if (!this.hoverList) this.hoverList = true
    },
    listLeave () {
      setTimeout(() => { this.hoverList = false }, 100)
    }
  },
  props: ['cdata'],
  computed: {
    showBox () {
      if (this.hoverList || this.hoverBox) return true
      else return false
    },
    boxData () {
      let arr = []
      let i
      let boxData = this.cdata[this.hoverIndex].products
      for (i = 0; i < boxData.length; i += 6) {
        arr.push(boxData.slice(i, i + 6))
      }
      this.boxStyle.width = 993 / 4 * arr.length + 'px'
      return arr
    }
  },
  data () {
    return {
      hoverIndex: 0,
      hoverList: false,
      hoverBox: false,
      boxStyle: {}
    }
  }
}
</script>
