<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="(item,id) of recommendList" :key="id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          
        </div>
      </li>
    </ul>
  </div>
  
</template>

<script>
export default {
  name: 'HomeWeekend',
  data() {
    return {
      recommendList:[{
        id:'0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/14/1cf5dc2ecbfc16.jpg_r_640x214_b4b3a58a.jpg',
        title:'最美丝路行',
        desc:'情系西北，中国梦丝路行'
      },{
        id:'0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1507/61/a7564da6033311.jpg_r_640x214_cc570e76.jpg',
        title:'激情漂流，嗨翻夏日',
        desc:'漂起来，展现你的“湿身”诱惑'
      },{
        id:'0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1506/37/8061eef0d08cd9.jpg_r_640x214_71ddceaf.jpg',
        title:'寻觅凉爽一夏',
        desc:'夏天不难熬，盘点夏日避暑乘凉好去处'
      }]
    }
     
  }
}
</script>

<style lang='stylus' scoped> 
@import '~styles/mixins.styl'
  .title
    margin-top:.2rem
    line-height :.8rem
    background: #eee
    text-indent: .2rem

  .item-img-wrapper
    height :0
    overflow :hidden
    padding-bottom :33.9%
    .item-img 
      width :100%
  .item-info
    padding : .1rem    
    .item-title
      line-height :.54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height :.4rem
      font-size: .28rem
      color :#ccc
      ellipsis()
        
</style>