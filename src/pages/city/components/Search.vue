<template>
<div>
    <div class="search">
      <input type="text" class="search-input" placeholder="输入城市名" v-model="keyworld">  
    </div>
    <div class="search-content" ref="search" v-show="keyworld">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key='item.id' @click="handleCityClick(item.name)">{{item.name}}</li>
        
        <li class="search-item border-bottom" v-show='hasNoData'>没有找到匹配数据</li>
        
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'

export default {
  
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyworld: '',
      list:[],
      timer: null
    }
  },
  computed:{
    hasNoData () {
      return !this.list.length
    }
  },
  methods:{
    handleCityClick(city){
      this.$store.dispatch('changeCity',city)
      this.$router.push('/')
    }
  },
  watch: {
    keyworld () {
      if(this.timer){
        clearTimeout(this.timer)
      }
      if (!this.keyworld){
        this.list = []
        return
      }
      this.timer =  setTimeout(() => {
        const result = []
        for (let i in this.cities){
          this.cities[i].forEach((value) => {
            if(value.spell.indexOf(this.keyworld)> -1 || value.name.indexOf(this.keyword) > -1){
              result.push(value)
            }
          })
        }
        this.list = result
      },100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
  
  
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
.search 
  height : .72rem 
  padding :0 .1rem 
  background :$bgColor 
  .search-input 
    box-sizing :border-box
    height:.62rem 
    line-height : .62rem
    width:100%
    text-align :center 
    border-radius : .06rem
    color :#666
    padding :0 .15rem 
.search-content
  z-index :1
  position :absolute 
  top: 1.58rem 
  left: 0 
  right: 0
  bottom: 0 
  overflow: hidden
  background :#eee
  .search-item
    line-height:.62rem 
    padding-left : .2rem 
    color:#666 
    background: #fff

</style>
