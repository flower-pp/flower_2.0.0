<template>
  <div class="slide">
    <el-carousel height="240px">
      <el-carousel-item 
        v-for="item in list" 
        :key="item.img">
        <img :src="item.img">
      </el-carousel-item>
    </el-carousel>
  </div>
</template>
<script>
export default {
  data: () => {
    return {
      list: [{
        url: '#abc',
        img: 'https://static2.flowerplus.cn/Static/newpc/images/light.jpg'
      }, {
        url: '#bsbsb',
        img: 'https://static2.flowerplus.cn/Static/newpc/images/qsdy.jpg'
      }, {
        url: '#sjfkajfj',
        img: 'https://static2.flowerplus.cn/Static/newpc/images/pzxx.jpg'
      }, {
        url: '#sjfkajfja',
        img: 'https://static2.flowerplus.cn/Static/newpc/images/ysg.jpg'
      }]
    }
  }
}
</script>
