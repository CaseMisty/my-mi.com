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
</style>

<template>
  <div class="main-box clearfix">
    <div class="box-hd">
      <h2 class="title">家电</h2>
      <ul class="more">
        <li>热门</li>
        <li>电视影音</li>
        <li>电脑</li>
        <li>家居</li>
      </ul>
    </div>
    <a href="" class="left">
      <img src="static/家电.jpg" width="234" height="614" alt="">
    </a>
    <ul class="list clearfix left">
      <product v-for="item of data.products" :data="item"></product>
      <div class="more left clearfix">
        <div class="brick-s a">
          <div class="title">米家扫地机器人</div>
          <div class="price">1699元</div>
          <img src="static/pms_1472609961.95298675!220x220.jpg" width="80" height="80"alt="">
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
  components: {
    product
  },
  props: ['data']
}
</script>
