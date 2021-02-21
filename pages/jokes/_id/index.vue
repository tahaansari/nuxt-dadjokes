
<template>
  <div>
      <nuxt-link to="/jokes">
        Back to jokes
      </nuxt-link>
      <h2>{{joke.title}}</h2>
  </div>
</template>

<script>
import axios from "axios";
export default {
    data(){
        return{
            joke:{}
        }
    },
    async created(){
        const response = await axios.get('https://jsonplaceholder.typicode.com/todos/'+this.$route.params.id)
        this.joke = response.data
    }
}
</script> 

<style>

</style>