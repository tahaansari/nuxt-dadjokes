<template>
  <div>
    <h2>Jokes Page</h2>
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam optio
      non beatae esse ea explicabo quaerat quae, perferendis temporibus eum,
      tenetur officia quas labore voluptas iste incidunt nam repellat ratione.
    </p>
    <searchJoke @searchJoke="searchJoke" />
    <joke
      v-for="joke in jokes"
      :key="joke.id"
      :joke="joke.title"
      :id="joke.id"
    />
  </div>
</template>

<script>
import axios from 'axios'
import joke from '../../components/Joke'
import searchJoke from '../../components/SearchJoke'
export default {
  data() {
    return {
      jokes: [],
    }
  },
  components: {
    joke,
    searchJoke,
  },
  async created() {
    try {
      const response = await axios.get(
        'https://jsonplaceholder.typicode.com/todos/'
      )
      this.jokes = response.data
    } catch (err) {
      console.log('error is ' + err)
    }
  },
  methods: {
    searchJoke(title) {
      alert('search joke  ' + title)
    },
  },
}
</script>

<style></style>
