<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item,id) of recommendList" :key="id">
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
  
</template>

<script>
export default {
  name: 'HomeRecommend',
  data() {
    return {
      recommendList:[{
        id:'0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_200x200_7690e4cd.jpg',
        title:'北京欢乐谷',
        desc:'游乐世界，主题公园'
      },{
        id:'0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201401/06/3fbbddda915cb7637439d484440d36be.jpg_200x200_a54e87dd.jpg',
        title:'杭州云曼温泉',
        desc:'游乐世界，主题公园'
      },{
        id:'0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/30/0c4071981e46cf9ce0812b56522ebb17.jpg_200x200_0c7e5a75.jpg',
        title:'虎啸峡漂流',
        desc:'游乐世界，主题公园'
      },{
        id:'0004',
        imgUrl: 'http://img1.qunarzz.com/wugc/p3/201206/02/45e5e7cf0c1ee5b393835fbb.jpg_200x200_9c6e5b18.jpg',
        title:'西溪国家湿地公园',
        desc:'游乐世界，主题公园'
      },{
        id:'0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/27/8211cadd5d9fefeaa044c5b7eefc695d.jpg_200x200_38791bd1.jpg',
        title:'千岛湖',
        desc:'游乐世界，主题公园'
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
  .item
    overflow hidden
    display :flex
    height :1.9rem
    
    .item-img 
      width :1.7rem
      height: 1.7rem
      padding :.1rem 
    .item-info
      flex :1  
      padding: .1rem 
      min-width :0
      .item-title
        line-height :.54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height :.4rem
        color :#ccc
        ellipsis()
      .item-button
        line-height :.44rem 
        background :#ff9300
        padding :0 .2rem 
        border-radius :.06rem
        margin-top .16rem
        color: #fff
</style>