<template>
  <div id="app" style="background-image : url('imgs/bg.jpg')">
    <HelloWorld msg="" />
    <csbutton/>
    
    <h1>{{csbutton}}</h1>
    <div class="row"> 
      <div class="col-6"><button label="Restart" /></div>
      <div class="col-6"><button label="Attack" /></div>
      <div class="col-6"><button label="Special Attack" /></div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import csbutton from './components/csbutton.vue'
export default {
  name: "App",
  components: {
    HelloWorld,
    csbutton,
  },
  data: function () {
    return {
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 100px;
}
</style>
