<template>
  <h1>Watcher Properties</h1>
  <h2>{{ volume }}</h2>
  <button @click="volume -=5">minus</button>
  <button @click="volume +=5">plus</button>
  <input type="text" v-model="movie">
  <input type="text" v-model="movieInfo.title">
  <input type="text" v-model="movieInfo.actor">
</template>

<script>

export default {
  name: 'AppSeven',
  data() {
    return {
      volume: 0,
      movie: '',
      movieInfo: {
        title: '',
        actor: ''
      }
    }
  },
  methods: {
  },
  computed: {
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue===15 && newValue > oldValue) {
        alert('this is alert')
      }
    },
    movie: {
      handler(newValue) {        
        console.log(`calling API ${newValue}`);
      }
    },
    movieInfo: {
      handler(newValue) { 
        console.log(`calling API title ${newValue.title} and actor ${newValue.actor}`);
      },
      deep:true,
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
