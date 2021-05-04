<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    {{joke}}
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'



export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data(){
    return {
      joke: Object
    }
  },
  mounted: function (){
    fetch('https://official-joke-api.appspot.com/random_joke', {
      method: 'get'
    })
        .then((response) => {
          return response.json()
        })
        .then((jsonData) => {
          this.joke = jsonData
        })
  }
}




</script>
