<style lang="scss" scoped>
.brick {
  position: relative;
  z-index: 1;
  float: left;
  width: 234px;
  margin-left: 14px;
  margin-bottom: 14px;
  height: 300px;
  -webkit-transition: all .2s linear;
  transition: all .2s linear;
  padding: 34px 0 20px;
  background: #fff;
  &:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
  }
}
a {
  color: #000;
}
.title {
    margin: 0 10px;
    font-size: 14px;
    font-weight: 400;
    text-align: center;
}
.des {
  margin: 0 10px 10px;
  height: 18px;
  font-size: 12px;
  text-align: center;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
  color: #b0b0b0;
}
.price {
    margin: 0 10px 10px;
    text-align: center;
    color: #ff6700;
}
.review-wrapper {
    position: absolute;
    bottom: 0;
    left: 0;
    z-index: 3;
    width: 234px;
    height: 0;
    overflow: hidden;
    background: #ff6700;
    opacity: 0;
    filter: alpha(opacity=0)\9;
    transition: all .2s linear;
    p {
      font-size: 12px;
      text-align: left
    }
}
.review {
    margin: 10px auto 5px auto;
    color: #fff;
    width: 174px;
    height: 36px;
}
.author {
    color: rgba(255,255,255,0.6);
    width: 174px;
    height: 36px/2;
    margin: 0 auto;
}
.brick:hover .review-wrapper{
    height: 76px;
    opacity: 1;
    filter: alpha(opacity=100)\9;
}

</style>

<template>
  <li class="brick">
    <a :href="data.href">
      <img :src="data.src" :alt="data.name" width="150" height="150">
      <p class="title">{{data.name}}</p>
      <p class="des">{{data.des}}</p>
      <p class="price">{{data.price}}元</p>
      <div class="review-wrapper">
        <p class="review">{{data.comment.text}}</p>
        <p class="author">来自于 {{data.comment.user}} 的评价</p>
      </div>
    </a>
  </li>
</template>

<script>
export default {
  props: ['data'],
  data () { }
}
</script>
