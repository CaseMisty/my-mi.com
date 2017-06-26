<style lang="scss">
@import './assets/_all.scss';
* {
  font: 14px/1.5 "Helvetica Neue",Helvetica,Arial,"Microsoft Yahei","Hiragino Sans GB","Heiti SC","WenQuanYi Micro Hei",sans-serif;
  text-align: center;
  // color: #2c3e50;
  margin: 0;
  padding: 0;
  border: 0;
  list-style-type: none;
  box-sizing: border-box!important;
}
html,
body {
  width: 100%;
}
a {
  text-decoration: none;
}
a:hover { 
  color: $米橘 ;
}
.ir {
  display: block;
  text-align: left;
  text-indent: -9999em;
  overflow: hidden;
}
.clearfix::after {
  content: '.';
  display: block;
  clear: both;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}
.site-ad-bar {
  width: 100%;
  height: 120px;
  background-repeat: no-repeat;
  background-position: center 0;
}
.container {
  width: 1226px;
  margin: {
    left: auto;
    right: auto;
  }
}
.list-service {
  padding: 27px 0;
  border-bottom: 1px solid #e0e0e0;
  li {
    float: left;
    width: 19.8%;
    height: 25px;
    border-left: 1px solid #e0e0e0;
    a {font-size: 16px; color:$深灰; transition: 0.3s; &:hover{color: $米橘;}}
    line-height: 25px;
    text-align: center;
    &:first-child{border-left: none;}
  }
}
.site-info .logo {
  float: left;
  width: 57px;
  height: 57px;
  margin-right: 10px;
}
.info-test {
  float: left;
  $a-size: 12px;
  p {
    color: #b0b0b0;
    text-align: left;
    font-size: $a-size;
  }
  a {color: $浅灰;font-size: $a-size;}
  a:hover{color: $米橘;}
  .sites>a {
    line-height:  $a-size+2;
    display: inline-block;
    height:  $a-size;
    color: $深灰;
    padding: 0 5px;
    border-left: 1px solid $深灰;
    &:first-child {
      border-left: none;
      padding-left: 0;
    }
    &:hover {color: $米橘;}
  }
}
.info-links {
  float: left;
  margin-left: 30px;
}
.info-links img{
    width: auto;
    height: 28px;
    margin-left: 7px;
}
.site-info .slogan {
    clear: both;
    margin: 30px auto 0;
    width: 267px;
    height: 19px;
}
.site-info {padding: 30px 0;}
.footer-links {
  padding: 40px 0;
  .col-links {
    float: left;
    width: 160px;
    height: 112px;
    margin: 0;
    dt, dd{
      text-align: left;
    }
    dt {
      margin: -1px 0 26px;
      font-size: 14px;
      line-height: 1.25;
      color: #424242;
    }
    dd a{
      margin: 10px 0 0;
      font-size: $小号;
      color: $浅灰;
    }
  }
  .col-contact {
    float: right;
    width: 251px;
    height: 112px;
    border-left: 1px solid #e0e0e0;
    text-align: center;
    color: #616161;
    .phone {
      margin: 0 0 5px;
      font-size: 22px;
      line-height: 1;
      color: #ff6700;
    }
    p {
      margin: 0 0 16px;
      font-size: $小号;
      span {font-size: inherit;}
    }
  }
}
.btn {
    display: inline-block;
    width: 158px;
    height: 38px;
    padding: 0;
    margin: 0;
    border: 1px solid $浅灰;
    font-size: 14px;
    line-height: 38px;
    text-align: center;
    color: $浅灰;
    cursor: pointer;
    -webkit-transition: all .4s;
    transition: all .4s;
    &:hover{color: $浅灰; text-decoration: none;}
}
.btn-small {
    width: 118px;
    height: 28px;
    font-size: $小号;
    line-height: 28px;
}
.btn-line-primary {
    border-color: $米橘;
    background: #fff;
    color: $米橘;
    &:hover{color: #fff;background-color: $米橘;}
}
.site-topbar {
  position: relative;
  z-index: 30;
  height: 40px;
  color: #b0b0b0;
  background: #333;
  a {
    color: $浅灰;
    font-size: $小号;
    &:hover{color: #fff!important;}
  }
  .topbar-nav {
    float: left;
    height: 40px;
    line-height: 40px;
    overflow: hidden;
    a {
      margin-left: 10px;
      margin-right: 10px;
      display: inline-block;
      &:first-child{margin-left: 0;}
      
    }
  }
  .topbar-cart {
    float: right;
    width: 120px;
    position: relative;
    margin-left: 15px;
    background-color: #404040;
    a {
      line-height: 40px;
    }
    &:hover {
      background: #fff;
      a {
        color: $米橘;
        &:hover{color:$米橘!important;}
      }
      .cart-menu {
        height: 100px;
        bottom: -100;
      }
    }
    .cart-menu{
      overflow: hidden;
      width: 316px;
      // height: 100px;
      background-color: #fff;
      z-index: 29;
      position: absolute;
      box-shadow: 0px 2px 10px rgba(0,0,0,0.15);
      right: 0;
      bottom: -100px;
      color: #000;
      line-height: 100px;
      font-size: $小号;
      height: 0;
    }
  }
  .topbar-info {
    line-height: 40px;
    position: relative;
    float: right;
    height: 40px; 
    a {
      padding: 0 5px;
    }
  }
}
.cart-enter-active, .cart-leave-active{
  transition: 0.5s;
}
.cart-leave-active{
  transform: translateY(-100px);
}
.cart-enter{
  // transform: translateY(-100px);
}
.site-header {
  .container{padding-top: 22px;}
  position: relative;
  z-index: 20;
  height: 100px;
  .header-logo {
    float: left;
    a {display: block; float: left;}
  }
  .doodle {
    height: 55px;
    width: 165px;
    margin-left: 14px;
  }
  .header-nav {
    width: 850px - 165px;
    float: left;
  }
  .nav-category{
    height: 70px;
    li {
      float: left;
      height: 100%;
      padding: 15px 10px;
      cursor: pointer;
      font-size: 16px;
      &:hover{color: $米橘;}
      a{
        display: block;
        width: 100%;
        height: 100%;
        font-size: 16px;
        color: #000;
        &:hover{color: $米橘;}
      }
    }
  }
}
.header-search {
  &:hover input{
    border-color: $浅灰;
  }
  float: right;
  width: 296px;
  height: 50px;
  position: relative;
  .search-text {
    position: absolute;
    text-align: left;
    top: 0;
    right: 51px;
    z-index: 1;
    width: 223px;
    height: 50px;
    padding: 0 10px;
    border: 1px solid #e0e0e0;
    font-size: 14px;
    font-family: 'sontti';
    line-height: 48px;
    outline: 0;
    transition: all 0.3s;
  }
  .search-btn {
    position: absolute;
    right: 0;
    top: 0;
    z-index: 2;
    width: 52px;
    height: 50px;
    border: 1px solid #e0e0e0;
    font-size: 18px;
    line-height: 18px;
    background: #fff;
    color: #616161;
    outline: 0;
    transition: all 0.3s;
  }
  .search-hot-words {
    position: absolute;
    top: 14px;
    right: 62px;
    z-index: 2;
    text-align: right;
    a {
      display: inline-block;
      margin-left: 5px;
      padding: 0 5px;
      font-size: $小号;
      background: #eee;
      color: #757575;
      -webkit-transition: all .2s;
      transition: all .2s;
    }
  }
  .search-hot-words a, .search-btn{
    &:hover{
      color: #fff;
      background-color: $米橘;
    }
  }
}
.fade-enter-active{
  transition: 0s;
}
.fade-enter,.fade-leave-active{
  opacity: 0;
}
.fade-leave-active{
  transition-delay: 0.5s;
  transition-duration: 0.3s;
}

.header-nav-menu{
  height: 230px;
  box-shadow: 0 3px 4px rgba(0,0,0,0.18);
  position: absolute;
  z-index: 50;
  width: 100%;
  border-top: 1px solid #e0e0e0;
  background: #fff;
  left: 0;
  top: 250px;
  ul {
    width: 100%;
    li {
      float: left;
      width: 204px;
      height: 201px;
      position: relative;
      &::before{
        position: absolute;
        left: 0;
        top: 35px;
        z-index: 1;
        width: 1px;
        height: 100px;
        content: "";
        background-color: #e0e0e0;
      }
      &.first::before{display: none;}
      .des {
        position: absolute;
        // display: inline-block;
        left: (204px/2)-35px;
        height: 18px;
        font-size: $小号;
        line-height: 14px;
        padding: 1px 20px;
        border: 1px solid #ff6700;
        color: #ff6700;
      }
      img {
        margin-top: 30px;
      }
      .product-name {
        padding-top: 15px;
        font-size: $小号;
        line-height: 20px;
        color: #333;
      }
      .price {
        color: $米橘;
        font-size: $小号;
      }
      a {
        display: block;
        position: absolute;
        bottom: 0;
        width: 100%;
        height: 100%;
      }
    }
  }
}
@font-face {
  font-family: 'iconfont';
  src: url('font/iconfont.eot');
  src: url('font/iconfont.eot?#iefix') format('embedded-opentype'),
  url('font/iconfont.woff') format('woff'),
  url('font/iconfont.ttf') format('truetype'),
  url('font/iconfont.svg#iconfont') format('svg');
}
.iconfont{
  font-family:"iconfont" !important;
  font-size:16px;font-style:normal;
  -webkit-font-smoothing: antialiased;
  -webkit-text-stroke-width: 0.2px;
  -moz-osx-font-smoothing: grayscale;
}
i:hover {
  cursor: default;
}
.list-service .iconfont{
  font-size: 24px;
  line-height: 24px;
  // margin-right: 6px;
  vertical-align: -3px;
}
</style>
<template>
  <div id="app">
    <div class="site-ad-bar" :style="`background-image: url(${adImgSrc})`"></div>
    <div class="site-topbar">
      <div class="container">
        <div class="topbar-nav">
          <a href="" v-for="item of siteData.topbarNav">{{item}}</a>
        </div>
        <div class="topbar-cart" @mouseenter="showCart=true" @mouseleave="showCart=false">
          <a href="" >
            <i class="iconfont">&#xe60e;</i>
            购物车
            <span>( 0 )</span>
          </a>
          <transition name="cart">
            <div class="cart-menu" v-if="showCart">
              购物车中还没有商品，赶紧选购吧！
            </div>
          </transition>
        </div>
        <div class="topbar-info">
          <a href="">登录</a>
          <a href="">注册</a>
          <a href="">消息通知</a>
        </div>
      </div>
    </div>
    <div class="site-header">
      <div class="container clearfix">
        <div class="header-logo clearfix">
          <a href="http://www.mi.com/index.html" class="logo" 
          :style="{height: '55px', width: '55px', backgroundImage:'url(static/logo-footer.png)'}"></a>
          <a href="" class="doodle" style="background-image: url(static/doodle.gif);"></a>
        </div>

        <div class="header-nav">
          <ul class="nav-category clearfix" @mouseenter="navMenuHover=true" @mouseleave="navMenuHover=false">
            <li v-for="(item, index) of siteData.headerNav" @mouseenter="changeNavMenu(index)">{{item.title}}</li>
            <li><a href="http://www.mi.com/service/">服务</a></li>
            <li><a href="http://www.xiaomi.cn/">社区</a></li>
          </ul>
        </div>

        <div class="header-search">
          <form action="">
            <input type="text" class="search-text" v-model="searchText" @focus="hotWords(true)" @blur="hotWords(false)">
            <button class="search-btn iconfont">&#xe608;</button>
            <transition name="fade">
              <div class="search-hot-words" v-if="showHotWords">
                <a href="http://item.mi.com/product/10000031.html">红米4X 699元起</a>
                <a href="http://www.mi.com/buytv/">电视4A</a>
              </div>
            </transition>
          </form>
        </div>
      </div>
    </div>

    <!--标题栏一堆产品的展示导航-->
    <transition name=fade>
      <div class="header-nav-menu" v-if="showNavMenu" @mouseleave="navHover=false" @mouseenter="navHover=true">
        <div class="container">
          <ul class="clearfix">
            <li v-for="(item,index) of siteData.headerNav[navIndex].products" :class="{first:index===0}">
              <div v-if="item.des" class="des">{{item.des}}</div>
              <img :src="item.src" alt="" width="160px" height="110px">
              <div v-html="item.name" class="product-name"></div>
              <div v-if="item.price" class="price">{{item.price}}</div>
              <a :href="item.href"></a>
            </li>
          </ul>
        </div>
      </div>
    </transition>

    <router-view></router-view>
    <div class="site-footer">
      <div class="container">
        <ul class="list-service clearfix">
          <li>
            <a href="">
              <i class="iconfont">&#xe62e;</i>
              预约维修服务
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont">&#xe776;</i>
              7天无理由退货
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont">&#xe606;</i>
              15天免费换货
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont">&#xe6a8;</i>
              满150元包邮
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont">&#xe635;</i>
              520余家售后网点
            </a>
          </li>
        </ul>
        <div class="footer-links clearfix">
          <dl class="col-links" v-for="item of siteData.footerLinks">
            <dt>{{item.title}}</dt>
            <dd v-for="link of item.links">
              <a :href="link.href">{{link.name}}</a>
            </dd>
          </dl>
          <div class="col-contact">
            <p class="phone">400-100-5678</p>
            <p>
              <span class="serviceTime-normal">周一至周日 8:00-18:00</span>
              <br>
              (仅收市话费)
            </p>
            <a class="btn btn-small btn-line-primary" href="">
              <i class="iconfont"></i>
              24小时在线客服
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="site-info">
      <div class="container clearfix">
        <p class="logo ir" :style="`background: url(${footerLogo}) no-repeat 50% 50%;`">小米官网</p>
        <div class="info-test">
          <p class="sites">
            <a v-for="item of siteData.footerInfoSites" :href="item.href">{{item.name}}</a>
          </p>
          <p>
            &copy;<a href="http://www.mi.com/">mi.com</a>京ICP证110507号 <a href="http://www.miitbeian.gov.cn/">京ICP备10046444号</a> <a href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802020134">京公网安备11010802020134号</a> <a href="http://c1.mifile.cn/f/i/2013/cn/jingwangwen.jpg">京网文[2014]0059-0009号</a>
            <br>
            违法和不良信息举报电话：185-0130-1238，本网站所列数据，除特殊说明，所有数据均出自我司实验室测试
          </p>
        </div>
        <div class="info-links">
          <a v-for="item of siteData.footerInfoImgs" :href="item.href"><img :src="item.src" alt="??"></a>
        </div>
      </div>
      <div class="slogan" :style="`background: url(static/fashao.png) no-repeat center 0;`"></div>
    </div>
  </div>
</template>

<script>
import siteData from './assets/data.js'
export default {
  data () {
    return {
      adImgSrc: require('./assets/head-ad.jpg'),
      footerLogo: require('./assets/logo-footer.png'),
      siteData,
      showCart: false,
      showHotWords: true,
      searchText: '',
      navIndex: 0,
      navMenuHover: false,
      navHover: false
    }
  },
  computed: {
    showNavMenu () {
      return this.navMenuHover || this.navHover
    }
  },
  methods: {
    hotWords (onFocus) {
      if (this.searchText || onFocus) {
        this.showHotWords = false
      } else this.showHotWords = true
    },
    changeNavMenu (index) {
      this.navIndex = index
    }
  },
  name: 'app'
}
</script>
