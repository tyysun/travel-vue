<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for='item of swiperList' :key='item.id'>
        <img class="swiper-img" :src="item.imgUrl" alt="">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data() {
    return {
      swiperOption:{
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1805/e5/59fad13a64807d02.jpg_750x200_713ae984.jpg"
      },{
        id: '0002',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1609/47/0cfdc871ac183702.jpg_750x200_f6896acd.jpg" 
      },{
        id: '0003',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1703/c1/681faf4fa8ae6e02.jpg_750x200_66a2f930.jpg" 
      }]
    }
  }
}
</script>

<style lang='stylus' scoped> 
.wrapper >>> .swiper-pagination-bullet-active 
  background: #fff
.wrapper
  width: 100%
  height: 0
  overflow: hidden
  padding-bottom: 26.6%
  background: #eee 
  .swiper-img
    width :100%
</style>