<template>
  <div>
    <router-link to="/">
      <i class="big arrow left icon"></i>
    </router-link>

    <br/>
    
    <WeatherPanel 
      v-bind:details="details"
      v-bind:city="city"
      v-bind:loading="loading"
    />
  </div>
</template>

<script>
import axios from 'axios';
import WeatherPanel from '@/components/WeatherPanel.vue'

export default {
  name: 'weather',
  components: {
    WeatherPanel
  },
  data() {
    return {
        city: '',
        details: [],
        loading: true
    }
  },
  methods: {
    getWeatherData: function() {
      axios.get('https://cors-anywhere.herokuapp.com/' + 'https://www.metaweather.com/api/location/' + this.$route.params.woeid)
        .then((response) => {
            this.loading = false;
            this.details = response.data.consolidated_weather;
            this.city = response.data.title;
        })
    },
  },
   mounted() {
    this.getWeatherData()
  }
}
</script>

<style scoped>
  i {
    float: left;
    padding: 30px;
  }
</style>