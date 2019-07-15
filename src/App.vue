<template>
  <div id="app">
    <router-view id="content" />
  </div>
</template>

<script>

export default {
  name: 'app'
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Special+Elite|Underdog&display=swap');

html {
  background: #222;
  background: radial-gradient(#111, #333);
}
body {
  margin: 0 50px;
}

#app {
  font-family: 'Underdog', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #3070b1;
  margin-top: 60px;
}

img {
  margin: auto;
  display: block;
}

h1 {
  text-align: center;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
