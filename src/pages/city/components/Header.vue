<template>
  <div class="header">
    
    城市选择
    <router-link to="/">
    <div class="iconfont icon-Group-left header-back"></div>
    </router-link>
  </div>
</template>

<script>


export default {
  name: 'CityHeader',
  components: {
    
  },
  data () {
    return {
      
    }
  },
 
  methods:{
    
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
  .header 
    height: .86rem 
    line-height : .86rem 
    text-align: center
    overflow: hidden
    color: #fff
    background : $bgColor
    font-size :.32rem
    position :relative
    .header-back
      position :absolute
      width :.64rem
      text-align :center
      font-size :.4rem
      top :0
      left :0
      color: #fff
</style>
