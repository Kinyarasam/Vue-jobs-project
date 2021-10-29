<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link :to="{ name: 'About' }">About</router-link>  |
    <router-link :to="{ name: 'Jobs' }">Jobs</router-link>
  </div>

  <button @click="redirect">Redirect</button>
  <button @click="back">Go back</button>
  <button @click="forward">Go Forward</button>

  <router-view/>

  
</template>

<script>

export default {
  methods: {
    redirect(){
      this.$router.push({ name: 'Home' })
    },
    back() {
      this.$router.go(-1)
    },
    forward() {
      this.$router.go(1)
    }
  }
}
</script>


<style>
body{
  background:rgba(205,230,230,0.9);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 10px;
 
}

#nav a.router-link-exact-active {
  color: white;
  background: crimson;
  box-shadow: 2px 2px 8px#2c3e50 ;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 10px;
}
</style>
