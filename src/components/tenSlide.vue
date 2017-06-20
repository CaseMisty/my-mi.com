<style lang="scss" scoped>
$浅灰: #b0b0b0;
$深灰: #757575;
$米橘: #ff6700;
$小号: 12px;
.clearfix::after {
  content: '';
  display: block;
  clear: both;
  height: 0;
  overflow: hidden;
  visibility: hidden;
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
      border-top-width: 2px;
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
.goods-list-move {
  transform: translateX(-1240px);
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
</style>

<template>
<div class="home-star-goods" @mouseenter="clearInv()" @mouseleave="runInv()">
  <div class="container">
    <div class="box-hd clearfix">
      <h2 class="title">{{tenSlideTitle}}</h2>
      <div class="more clearfix">
        <div class="left" :class="{'move-active': !goodsOnLeft}" @click="checkGoods(true)">←</div>
        <div class="right" :class="{'move-active': goodsOnLeft}" @click="checkGoods(false)">→</div>
      </div>
    </div>
    <div class="box-bd" style="height:340px;">
      <ul class="goods-list" :class="{'goods-list-move': goodsOnLeft}" style="width:2480px;height:340px;">
        <li v-for="(item,index) of goodsList" :class="`rinbow-color-${index}`">
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
</template>

<script>

export default {
  props: {
    goodsList: {
      type: Array
    },
    tenSlideTitle: {
      type: String,
      default: '小米明星单品'
    },
    inv: {
      type: Number,
      default: 3
    }
  },
  data () {
    return {
      goodsOnLeft: true
    }
  },
  methods: {
    runInv () {
      this.invId = setInterval(() => {
        this.moveGoods()
      }, this.inv * 1000)
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
