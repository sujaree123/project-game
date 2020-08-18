<template>
  <div>
    <button @click="upFunction" class="btn btn-warning">{{label}}</button>
    <p v-bind:style="{fontSize: fsize + 'px'}">{{csbutton}}</p>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      button: 0,
      fsize: 50,
    };
  },
  props: {
    label: String,
  },
  medthod: {
    randomDamageSpi: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    randomDamageIron: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    randomDamageHulk: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },

  },
};
</script>
<style>
</style>