<style lang="scss" scoped>
@import './assets/_all.scss';
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
.page-main {
  padding-top: 60px;
  background-color: #f5f5f5;
}
</style>

<template>
  <div>
    <div class="head-slide">
      <div class="container">
        <headSlide>
          <siteCategory :cdata="siteData.siteCategory"></siteCategory>
        </headSlide>
        <div class="home-hero-sub clearfix">
          <ul class="home-channel-list clearfix">
            <li v-for="(item,index) of siteData.homeHeroSub.homeChannelList" 
            :class="['channel-' + index]">
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
    <ten-slide :goodsList="siteData.goodsList">
    </ten-slide>
    <div class="page-main">
      <div class="container clearfix">
        <miProduct :data="siteData.home.class[0]"></miProduct>
      </div>
    </div>
  </div>
</template>

<script>
import headSlide from './components/headSlide.vue'
import tenSlide from './components/tenSlide'
import siteData from './assets/data.js'
import siteCategory from './components/siteCategory'
import miProduct from './components/mi-product'

export default {
  components: {
    headSlide,
    tenSlide,
    siteCategory,
    miProduct
  },
  data () {
    return {
      siteData
    }
  },
  methods: {
  },
  mounted () {
  }
}
</script>

