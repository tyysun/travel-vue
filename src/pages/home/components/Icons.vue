<template>
  <div class="icons">
    <swiper >
      <swiper-slide v-for='(page,index) of pages' :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
          </div>
          
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <!-- <div class="swiper-pagination"  slot="pagination"></div> -->
    
    </swiper>

  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data() {
    return {
      swiperOption:{
        pagination: '.swiper-pagination',
        loop: true
      },
      
      iconList: [{
        id: '0001',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
        desc: '景点的的是多少门票1'
      },{
        id: '0002',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png" ,
        desc: 'Q+精选'
      },{
        id: '0003',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png" ,
        desc: '游乐场'
      },{
        id: '0004',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png" ,
        desc: '必游榜单'
      },{
        id: '0005',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png" ,
        desc: '西湖'
      },{
        id: '0006',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png" ,
        desc: '夏日玩水'
      },{
        id: '0007',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png" ,
        desc: '宋城千古情'
      },{
        id: '0008',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png" ,
        desc: '千岛湖'
      },{
        id: '0009',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png" ,
        desc: '全部项目'
      }]
    }
  },
  computed: {
    pages (){
      const pages = []
      this.iconList.forEach((item,index)=>{
        const page = Math.floor(index/8)
        if(!pages[page]){
          pages[page]=[]
        }
        pages[page].push(item)
      } )
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped> 
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'

.icons >>> .swiper-container
  width :100%
  
  height: 0
  padding-bottom : 50%
.icons
  margin-top :.1rem
  .icon
    position :relative
    overflow :hidden
    float: left
    width: 25%
    padding-bottom : 25%
    
    height :0
    .icon-img
      position :absolute
      top:0
      left :0
      right :0
      bottom : .44rem
      box-sizing : border-box
      padding : .1rem
      .icon-img-content
        height :100%
        display :block
        margin : 0 auto 
    .icon-desc
      position :absolute
      
      left :0
      right :0
      bottom : 0
      line-height :.44rem
      height : .44rem
      text-align :center
      color: $darkTextColor
      ellipsis()
</style>