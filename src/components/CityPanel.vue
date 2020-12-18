<template>
  <div class="city">
    <div v-if='loading'> 
      <sui-button basic loading content="Loading" size="big"/> 
    </div>

    <div v-else> 
      <router-link :to="{ name: 'city', params: { woeid: passedWoeid }}">
          <sui-button basic size="big">
            <sui-header size="small">{{cityName}}</sui-header>
          </sui-button> 
      </router-link>
    </div>
  </div>
</template>

<script>
// import axios from 'axios';
export default {
  name: 'CityPanel',
  props: {
    passedWoeid: String,
    cityName: String
  },
  data() {
    return {
        // city: '',
        loading: false
    }
  },
  // methods: {
  //   getWeatherData: function() {
  //     axios.get('https://cors-anywhere.herokuapp.com/' + 'https://www.metaweather.com/api/location/' + this.passedWoeid)
  //       .then((response) => {
  //           this.city = response.data.title;
  //           this.loading = false;
  //       })
  //   }
  // },
  // mounted() {
  //   this.getWeatherData()
  // }
}
</script>

<style scoped>
  .ui.button {
    width: 250px;
    padding: 25px;
  }

  .ui.basic.button {
    box-shadow: .5px .5px 3px gray;
  }
</style>