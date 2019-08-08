<template>
  <div class="m-nav">
    <ul class="nav">
      <li class="list">
        <nuxt-link to="/my">个人中心</nuxt-link>
        <dl>
          <dd><nuxt-link to="/order">我的订单</nuxt-link></dd>
          <dd><nuxt-link to="/order">我的收藏</nuxt-link></dd>
          <dd><nuxt-link to="/order">抵用券</nuxt-link></dd>
          <dd><nuxt-link to="/order">账户设置</nuxt-link></dd>
        </dl>
      </li>
      <li>
        <nuxt-link to="/order">手机APP</nuxt-link>
      </li>
      <li class="list bd">
        <nuxt-link to="/center">商家中心</nuxt-link>
        <dl>
          <dd><nuxt-link to="/userCenter">登录商家中心</nuxt-link></dd>
          <dd><nuxt-link to="/coop">我想合作</nuxt-link></dd>
          <dd><nuxt-link to="/wap">免费手机开店</nuxt-link></dd>
          <dd><nuxt-link to="/kaipiao">商家申请开票</nuxt-link></dd>
        </dl>
      </li>
      <li class="list site">
        <nuxt-link to="/site">网站导航</nuxt-link>
        <div class="subContainer">
          <dl class="hotel">
            <dt>玫瑰</dt>
            <dd>红玫瑰</dd>
            <dd>粉玫瑰</dd>
            <dd>黄玫瑰</dd>
            <dd>绿玫瑰</dd>
            <dd>白玫瑰</dd>
          </dl>
          <dl class="food">
            <dt>百合</dt>
            <dd>康乃馨</dd>
            <dd>满天星</dd>
            <dd>雏菊</dd>
          </dl>
          <dl class="app">
            <dt>其他美好</dt>
            
            <dd>
              <a href="#">
                <img
                  src="https://www.netflorist.co.za/product-photos/230x293/RA3302.jpg"
                  title="糖果"
                  alt="糖果">
              </a>
            </dd>
            <dd>
              <a href="#">
                <img
                  src="https://www.netflorist.co.za/layout/banners/htmlslides/20180308/ThankYou_New.jpg"
                  title="礼物"
                  alt="礼物">
              </a>
            </dd>
            <dd>
              <a href="#">
                <img
                  src="https://www.netflorist.co.za/product-photos/230x293/PER6030.jpg"
                  title="家居"
                  alt="家居">
              </a>
            </dd>
          </dl>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {

  }
</script>

<style scoped>

</style>
