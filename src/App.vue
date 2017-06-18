<style lang="scss">
$浅灰: #b0b0b0;
$深灰: #757575;
$米橘: #ff6700;
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
  color: $米橘 !important;
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
    a {font-size: 16px;}
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
      font-size: 12px;
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
      font-size: 12px;
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
    font-size: 12px;
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
    font-size: 12px;
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
    &:hover {
      background: #fff;
      a {
        color: $米橘;
        &:hover{color:$米橘!important;}
      }
    }
    a {
      line-height: 40px;
    }
    .cart-menu{
      width: 316px;
      height: 100px;
      background-color: #fff;
      z-index: 29;
      position: absolute;
      box-shadow: 0px 2px 10px rgba(0,0,0,0.15);
      right: 0;
      bottom: -80px;
      color: #000;
      line-height: 100px;
      font-size: 12px;
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
.cart-enter,.cart-leave-active{
  transform: translateY(-20px);
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
            <i class="iconfont"></i>
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
    <div class="site-header"></div>
    <router-view></router-view>
    <div class="site-footer">
      <div class="container">
        <ul class="list-service clearfix">
          <li>
            <a href="">
              <i class="iconfont"></i>
              预约维修服务
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont"></i>
              7天无理由退货
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont"></i>
              15天免费换货
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont"></i>
              满150元包邮
            </a>
          </li>
          <li>
            <a href="">
              <i class="iconfont"></i>
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
      showCart: false
    }
  },
  name: 'app'
}
</script>
