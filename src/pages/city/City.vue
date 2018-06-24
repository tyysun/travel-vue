<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch :cities='cities'></CitySearch>
    <CityList :cities='cities' :hot='hotCities' :letter='letter'></CityList>
    <CityAlphabet :cities='cities' @change='handleLetterClick'></CityAlphabet>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
      
    }
  },
  mounted () {
    this.getCityInfo()
  },
 
  methods:{
    getCityInfo () {
      axios.get('/static/mock/city.json')
        .then(this.handleGetCityInfoSuccesd)
    },
    handleGetCityInfoSuccesd (res) {
      res = res.data 
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterClick (letter) {
      this.letter= letter
      
    }
  }
}
</script>

<style lang='stylus' scoped>

</style>
