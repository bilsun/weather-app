<template>
  <div class="weather">
    <div v-if='loading'> 
      <sui-header size="large">
        <br/><br/>
        Loading...
      </sui-header>
    </div>

    <div v-else> 
      <br>  
      <h1 is="sui-header">{{city}}</h1>
      <br/>

      <sui-button basic>
        <sui-header size="standard">Today</sui-header>
        {{this.details[0].weather_state_name}} <br/><br/>
        <div class='darkText'>
          Low: {{toFahrenheit(this.details[0].min_temp)}} 
          High: {{toFahrenheit(this.details[0].max_temp)}}
        </div>
      </sui-button> 

      <br><br>

      <sui-button basic>
        <sui-header size="standard">Tomorrow</sui-header>
        {{this.details[1].weather_state_name}} <br/><br/>
        <div class='darkText'>
          Low: {{toFahrenheit(this.details[1].min_temp)}} 
          High: {{toFahrenheit(this.details[1].max_temp)}}
        </div>
      </sui-button> 

      <br><br>
      
      <sui-button basic>
        <sui-header size="standard">In 2 Days</sui-header> 
        {{this.details[2].weather_state_name}} <br/><br/>
        <div class='darkText'>
          Low: {{toFahrenheit(this.details[2].min_temp)}} 
          High: {{toFahrenheit(this.details[2].max_temp)}}
        </div>
      </sui-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WeatherPanel',
  props: {
    city: String,
    loading: Boolean,
    details: Array
  },
  methods: {
    toFahrenheit(value) {
      return Math.round((9/5)*value + 32);
    }
  }
}
</script>

<style scoped>
  .ui.button {
    width: 250px;
    padding: 25px;
    cursor: context-menu;
  }

  .ui.basic.button {
    box-shadow: .5px .5px 3px gray;
  }

  .ui.standard.header {
    margin: 2px;
  }

  .darkText {
    color: black !important;
  }

  .ui.basic.button:active {
    background: transparent none !important;
  }
</style>