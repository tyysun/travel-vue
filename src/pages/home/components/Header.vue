<template>
  <div class='header'>
   <div class="header-left"><div class="iconfont icon-Group-left back-icon"></div></div>
   <div class="header-input"><span class="iconfont icon-Group-s"></span>输入城市/景点/游玩主题</div>
   <router-link to='/city'>
    <div class="header-right">{{this.city}}<span class="iconfont icon-Group-down"></span></div>
   </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'Header',
  computed:{
    ...mapState(['city'])
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
      min-width: 1.04rem
      padding: 0 .1rem
      float: right
      text-align: center
      color: #fff

       
</style>
// 1rem = html font-size = 50px