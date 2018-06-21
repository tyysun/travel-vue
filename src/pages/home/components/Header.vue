<template>
  <div class='header'>
   <div class="header-left"><div class="iconfont icon-Group-left back-icon"></div></div>
   <div class="header-input"><span class="iconfont icon-Group-s"></span>输入城市/景点/游玩主题</div>
   <div class="header-right">{{this.city}}<span class="iconfont icon-Group-down"></span></div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    city: String
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
  .header
    display: flex
    line-height: .86rem 
    background-color: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align: center
        font-size:.4rem
    .header-input
      flex: 1  
      background: #fff
      border-radius: .1rem
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      height: .62rem
      line-height: .62rem
      color: #ccc
    .header-right
      width: 1.24rem
      float: right
      text-align: center

       
</style>
// 1rem = html font-size = 50px