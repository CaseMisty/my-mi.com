<style lang="scss" scoped>
$米橘: #ff6700;
.reac {
  width: 100%;
  height: 460px;
  text-align: left;
}
.home-hero-sub{
  margin-bottom: 26px;
  margin-top: 14px;
}
.home-channel-list {
  margin: 0;
  padding: 3px;
  list-style-type: none;
  font-size: 12px;
  text-align: center;
  background: #5f5750;
  width: 234px;
  height: 170px;
  float: left;
}
.home-channel-list li {
  position: relative;
  float: left;
  width: 76px;
  height: 82px;
  padding: 0 3px;
  border: 1px solid #665e57;
  &::before{
    top: -1px;
    left: 6px;
    width: 64px;
    height: 1px;
  }
  &::after{    
    position: absolute;
    content: "";
    background: #665e57;}
  a{
    display: block;
    width: 70px;
    height: 64px;
    font-size: 12px;
    line-height: 81px;
    color: rgba(255, 255, 255, 0.7);
    &:hover{
      color: #fff;
    }
  }
}
.home-promo-list {
  float: left;
  li {
    float: left;
    &:first-child {
      margin-left: 14px;
    }
    margin-left: 15px;
  }
}
.box-hd {
  position: relative;
  overflow: hidden;
  height: 58px;
  -webkit-font-smoothing: antialiased;
  .title {
    margin: 0;
    font-size: 22px;
    font-weight: 200;
    line-height: 58px;
    color: #333;
    text-align: left;
    width: 200px;
    float: left;
  }
  .more {
    width: 72px;
    height: 25px;
    float: right;
    // position: absolute;
    // right: 0;
    // margin-top: 10px;
    div{
      float: left;
      width: 36px;
      height: 24px;
      padding: 3px 5px;
      border: 1px solid #e0e0e0;
      font-size: 16px;
      line-height: 16px;
    }
    div.left {
      border-right: none;
    }
  }
}
</style>

<template>
  <div>
    <div class="head-slide">
      <div class="container">
        <head-slide>
          <div style="position: absolute; left: 0; top: 0;">faaqqqq</div>
        </head-slide>
        <div class="home-hero-sub clearfix">
          <ul class="home-channel-list clearfix">
            <li v-for="(item,index) of siteData.homeHeroSub.homeChannelList" 
            :class="['channel-'+index]">
              <a :href="item.href">{{item.name}}</a>
            </li>
          </ul>
          <ul class="home-promo-list clearfix">
            <li v-for="item of siteData.homeHeroSub.homePromoList">
              <a :href="item.href">
                <img :src="item.src" alt="" width="316" height="170">
                </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div class="home-star-goods">
      <div class="container">
        <div class="box-hd clearfix">
          <h2 class="title">小米明星单品</h2>
          <div class="more clearfix">
            <div class="left">←</div>
            <div class="right">→</div>
          </div>
        </div>
        <div class="box-bd" style="height:340px;">
          <ul class="goods-list" style="width:2480px;height:340px;">
            <li></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import headSlide from './components/headSlide.vue'
import siteData from './assets/data.js'
export default {
  components: {
    headSlide
  },
  data () {
    return {
      siteData
    }
  }
}
</script>

