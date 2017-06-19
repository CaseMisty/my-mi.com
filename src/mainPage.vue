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
    margin-top: 20px;
    div{
      float: left;
      width: 36px;
      height: 24px;
      transition: color 0.3s;
      border: 1px solid #e0e0e0;
      color: $深灰;
      font-size: 16px;
      line-height: 18px;
    }
    div.left {
      border-right: none;
    }
    .move-active {
      cursor: pointer;
      &:hover{
        color: $米橘;
      }
    }
  }
}
.box-bd {
  $ul-width: 2480px;
  overflow: hidden;
  position: relative;
  .goods-list {
    position: absolute;
    transition: 0.5s;
    li {
      float: left;
      width: 234px;
      height: 340px;
      margin-left: 14px;
      background-color: #fafafa;
      transition: all 0.6s;
      border-top-width: 1px;
      border-top-style: solid;
      padding-top: 40px;
      position: relative;
      &:first-child {
        margin-left: 0;
      }
    }
    img {
      margin-bottom: 20px;
    }
    .desc {
      height: 18px;
      margin: 0 20px 12px;
      font-size: 12px;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
      color: #b0b0b0;
    }
    .price {
      color: $米橘;
      margin: 0;
      font-size: 14px;
      line-height: 21px;
    }
    a {
      color: #212121;
      line-height: 21px;
      font-size: 14px;
      display: block;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
    }
  }
}
.rinbow-color-0,.rinbow-color-5 {
  border-top-color: #ffac13;
}
.rinbow-color-1,.rinbow-color-6 {
  border-top-color: #83c44e;
}
.rinbow-color-2,.rinbow-color-7 {
  border-top-color: #2196f3;
}
.rinbow-color-3,.rinbow-color-8 {
  border-top-color: #e53935;
}
.rinbow-color-4,.rinbow-color-9 {
  border-top-color: #00c0a5;
}
.goods-list-move {
  transform: translateX(-1240px);
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
            <div class="left" :class="{'move-active': !goodsOnLeft}" @click="checkGoods(true)">←</div>
            <div class="right" :class="{'move-active': goodsOnLeft}" @click="checkGoods(false)">→</div>
          </div>
        </div>
        <div class="box-bd" style="height:340px;">
          <ul class="goods-list" :class="{'goods-list-move': goodsOnLeft}" style="width:2480px;height:340px;">
            <li v-for="(item,index) of siteData.goodsList" :class="`rinbow-color-${index}`">
              <img :src="item.src" :alt="item.name" width="160" height="160">
              <p class="name">{{item.name}}</p>
              <p class="desc">{{item.desc}}</p>
              <p class="price">{{item.price}}</p>
              <a :href="item.href"></a>
            </li>
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
      siteData,
      goodsOnLeft: true
    }
  },
  methods: {
    runInv () {
      this.invId = setInterval(() => {
        this.moveGoods()
      }, 5000)
    },
    clearInv () {
      clearInterval(this.invId)
    },
    moveGoods () {
      this.goodsOnLeft = !this.goodsOnLeft
    },
    checkGoods (clickLeft) {
      if (clickLeft !== this.goodsOnLeft) {
        this.moveGoods()
      }
    }
  },
  mounted () {
    this.runInv()
  }
}
</script>

