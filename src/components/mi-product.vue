<style lang="scss" scoped>
@import '../assets/_all.scss';
$width: 992px;
$height: 614px;
.list {
  width: $width;
  height: $height;
}
.left {
  float: left;
}
.box-hd {
    position: relative;
    height: 58px;
    -webkit-font-smoothing: antialiased;
    .title {
      margin: 0;
      font-size: 22px;
      font-weight: 200;
      line-height: 58px;
      color: #333;
      text-align: left;
    }
    .more {
      position: absolute;
      top: 0;
      right: 0;
      li {
        display: inline-block;
        padding-top: 12px;
        color: #424242;
        border-bottom: 2px solid transparent;
        transition: border-color .5s;
        cursor: pointer;
        margin-left: 30px;
        font-size: 16px
      }
    }
}
.main-box{
  margin-bottom: 30px;
}
.more {
  margin-left: 14px;
}
.brick-s{
  height: 143px;
  width: 234px;
  padding-top:50px;
    background: #fff;
    transition-duration: 0.3s;
  &:hover {
    transform: translateY(-3px);
    box-shadow: 0 5px 30px rgba(0,0,0,0.1);
  }
  margin-bottom: 14px;
  div {
    text-align: left;
  }
  .title {
    margin: 0 20px;
    font-size: 14px;
    font-weight: 400;
  }
  .price {
      margin: 0 20px 10px;
      color: #ff6700;
  }
}
 .a {
    position: relative;
  }
.a img {
  position: absolute;
  top: 40px;
  right: 20px;
}
.b {
  position: relative;
}
.b i{
  position: absolute;
  right: 40px;
  top: 30px;
  font-size: 50px;
  color: $米橘;
}
.to-top:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.2);
    transition: all 0.2s linear;
}
.cate-active {
  color: $米橘 !important;
  border-bottom: 1px solid !important;
}
</style>

<template>
  <div class="main-box clearfix">
    <div class="box-hd">
      <h2 class="title">{{data.title}}</h2>
      <ul class="more">
        <li v-for="(item,index) of data.class" :key="item.title" :class="{'cate-active': index===current}">{{item.title}}</li>
      </ul>
    </div>
    <div class="left">
      <template v-if="data.leftImage.length === 1">
        <a href="">
          <img :src="data.leftImage[0]" width="234" height="614" alt="" class="to-top">
        </a>
      </template>
      <template v-else>
        <p>
          <a href=""><img :src="data.leftImage[0]" width="234" height="300" alt="" class="to-top" style="margin-bottom: 8px;"></a>
        </p>
        <p>
          <a href=""><img :src="data.leftImage[1]" width="234" height="300" alt="" class="to-top"></a>
        </p>
      </template>
    </div>
    <ul class="list clearfix left">
      <product v-for="item of currentCate.products" :data="item" :key="item.id"></product>
      <div class="more left clearfix">
        <div class="brick-s a">
          <div class="title">{{currentCate.littleOne.name}}</div>
          <div class="price">{{currentCate.littleOne.price}}元</div>
          <img :src="currentCate.littleOne.src" width="80" height="80"alt="">
        </div>
        <div class="brick-s b">
          <p style="position: absolute; left: 30px; top: 50px; font-size: 1.5em;">
            浏览更多
          </p>
          <small style="position: absolute; left: 30px; top: 80px;">热门</small>
          <i class="iconfont">&#xe607;</i>
        </div>
      </div>
    </ul>
  </div>
</template>

<script>
import product from './product'
export default {
  data () {
    return {
      title: '家电',
      moreList: ['热门', '电视影音', '电脑', '家居'],
      currentCate: this.data.class[0],
      current: 0
    }
  },
  components: {
    product
  },
  props: ['data']
}
</script>
