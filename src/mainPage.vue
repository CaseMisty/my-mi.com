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

</style>

<template>
  <div class="head-slide">
    <div class="container">
      <head-slide>
        <div style="position: absolute; left: 0; top: 0;">faaqqqq</div>
      </head-slide>
      <div class="home-hero-sub row">
        <ul class="home-channel-list clearfix">
          <li v-for="(item,index) of siteData.homeHeroSub.homeChannelList" 
          :class="['channel-'+index]">
            <a :href="item.href">{{item.name}}</a>
          </li>
        </ul>
        <ul class="home-promo-list clearfix">
          <li>
            <a href=""><img src="" alt=""></a>
            </li>
        </ul>
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

