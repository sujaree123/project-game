<template>
<body>
  <div id="app">
    <csbutton msg />
  </div>
</body>
</template>

<script>
import csbutton from "./components/csbutton.vue";

export default {
  name: "App",
  components: {
    csbutton,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding: 3em;
}
body {
  background-image: url("./assets/img/bg.jpg");
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
