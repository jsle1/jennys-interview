<template>
<div>
    <!-- I created an input field that would take info and track what the user was typing
    then when the user clicks the button to send in the value. It would activae sendData Method" -->
  <input 
  placeholder="Enter a City!"
  type="text"
  v-on="$listeners"
  :value="value"
  @input="$emit('update', $event.target.value)">
    <button v-on:click="sendData()">Send</button>
</div>
</template>

<script>
import axios from "axios";
export default {
  data(){
      city: ''
      woeid: ''
  },
  /*
    Within the send data method, it would call the API to get the title of the city as well as the woeid and latt_long.
    The woeid would be used to get information for conslidated_weather where it would tell you about the weather conditions in the city
    latt_long would be used for the map feature to to place a marker on the map of the location of the city
  */
  methods: {
      sendData: function() {
          var app = this
          axios.get('https://www.metaweather.com/api/location/search/?query=' + app.city)
            .then(function(response) {
                app.city = response.data.title
                app.woeid = response.data.woeid
                app.latt_long = response.data.latt_long
            })
            .catch(function (error) {
                app.city = "Invalid City"
            })
      }
  }
}
</script>

<style scoped>

.filters {
  width: 800px;
  margin: 0 auto;
}

.filter {
  text-align: left;
}

.result {
  margin-top: 30px;
  text-align: left;
}

label {
  display: block;
}

</style>
