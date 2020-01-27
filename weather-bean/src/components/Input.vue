<template>
<div>
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
  methods: {
      sendData: function() {
          var app = app
          app.city = "Searching..."
          axios.get('https://www.metaweather.com/api/location/search/?query=' + app.city)
            .then(function(response) {
                app.city = response.data.title
                app.woeid = response.data.woeid
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
