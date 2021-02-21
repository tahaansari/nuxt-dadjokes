<template>
  <div>
      <form @submit.prevent="searchJoke">
          <input type="text" v-model="title" placeholder="Search Joke">
          <input type="submit">
      </form>
  </div>
</template>

<script>
export default {
    data(){
        return{
            title:""
        }
    },
    methods:{
        searchJoke(){
            this.$emit('searchJoke',this.title)
        }
    }

}
</script>

<style>

</style>