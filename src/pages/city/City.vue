<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch :cities="cities"></CitySearch>
    <CityList :cities="cities" :hot="hotCities" :letter="letter"></CityList>
    <CityAlphabet :cities="cities"
                  @change="handleLetterChange"></CityAlphabet>
  </div>
</template>

<script>
  import CityHeader from '../city/components/Header'
  import CitySearch from '../city/components/Search'
  import CityList from '../city/components/List'
  import CityAlphabet from '../city/components/Alphabet'
  import axios from 'axios'
    export default {
        name: "City",
      data(){
          return {
            cities:{},
            hotCities:[],
            letter:''
          }
      },
      components:{
          CityHeader,
          CitySearch,
          CityList,
          CityAlphabet
      },
      methods:{
          getCityInfo(){
            axios.get('/api/city.json').then(this.handleGetCityInfosucc)
          },
        handleGetCityInfosucc(res){
            res=res.data
            if(res.ret && res.data){
              const data=res.data
              this.cities=data.cities
              this.hotCities=data.hotCities
            }
        },
        handleLetterChange (letter) {
          this.letter = letter
        }
      },
      mounted(){
          this.getCityInfo()
      }
    }
</script>

<style lang="stylus" scoped>

</style>
