<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
    <CityList :cities='cities' :hot='hotCities'></CityList>
    <CityAlphabet :cities='cities'></CityAlphabet>
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
      hotCities: []
      
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
    }
  }
}
</script>

<style lang='stylus' scoped>

</style>
