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
      
    
    </swiper>

  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data() {
    return {
      
      iconList: [{
        id: '0001',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
        desc: '景点的的是多少门票1'
      },{
        id: '0002',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png" ,
        desc: '名胜古迹2'
      },{
        id: '0003',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png" ,
        desc: '游乐场3'
      },{
        id: '0004',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png" ,
        desc: '必游榜单4'
      },{
        id: '0005',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png" ,
        desc: '游乐场5'
      },{
        id: '0006',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png" ,
        desc: '名胜古迹6'
      },{
        id: '0007',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png" ,
        desc: '游乐场7'
      },{
        id: '0008',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png" ,
        desc: '全部项目8'
      },{
        id: '0009',
        imgUrl: "http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png" ,
        desc: '游乐场9'
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