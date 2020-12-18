<template>
  <div>
    <br/>
    <sui-header size="huge">Weather</sui-header> <br/>
    <CityPanel passedWoeid="2514815" cityName="Washington, DC"/> <br/> <!--DC-->
    <CityPanel passedWoeid="2379574" cityName="Chicago"/> <br/> <!--Chicago-->
    <CityPanel passedWoeid="2487956" cityName="San Francisco"/> <!--SF-->
  </div>
</template>

<script>
import CityPanel from '@/components/CityPanel.vue'

export default {
  name: 'home',
  components: {
    CityPanel
  }
}
</script>
