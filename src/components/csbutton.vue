<template>
  <div>
    <button @click="randomStart()" class="btn btn-dark mb-2">Start</button>
    <template v-if="s == 1">
      <div class="row">
        <div class="col">
          <button @click="randomDamage(1,70)" class="btn btn-warning mb-4 mr-2">Attack</button>
          <button @click="randomDamageSP(60,100)" class="btn btn-danger mb-4">Special Attack</button>
        </div>
      </div>
      <div class="container-fluid">
        <div class="row">
          <div class="col">
            <div class="alert alert-primary" role="alert">Hero : {{randomPlayer}}</div>
            <div class="alert alert-success" role="alert">HP : {{hp1}}</div>
            <img :src="image1" class="img-fluid" />
          </div>
          <div class="col">
            <div class="alert alert-primary" role="alert">Hero : {{randomMonster}}</div>
            <div class="alert alert-success" role>HP : {{hp2}}</div>
            <img :src="image2" class="img-fluid" />
          </div>
        </div>
      </div>
    </template>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      randomAttack: "",
      randomSpAttack: "",
      image1: "",
      image2: "",
      hp1: "",
      hp2: "",
      s: 0,
      win: "./assets/img/win.png",
      lose: "./assets/img/lose.png",
      player: [
        {
          name: "Anakin",
          hp: 450,
          image: "./assets/img/anakin.png",
        },
        {
          name: "Cell",
          hp: 270,
          image: "./assets/img/cell.png",
        },
        {
          name: "Darth Vader",
          hp: 360,
          image: "./assets/img/darth-vader.png",
        },
      ],
      randomPlayer: "",
      monster: [
        {
          name: "Doraemon",
          hp: 230,
          image: "./assets/img/doraemon.png",
        },
        {
          name: "Iron-man",
          hp: 510,
          image: "./assets/img/iron-man.png",
        },
        {
          name: "Thanos",
          hp: 500,
          image: "./assets/img/thanos.png",
        },
      ],
      randomMonster: "",
    };
  },

  methods: {
    randomStart: function () {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1 = this.player[chosenNumber1].hp;
      this.image1 = this.player[chosenNumber1].image;

      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2 = this.monster[chosenNumber2].hp;
      this.image2 = this.monster[chosenNumber2].image;

      this.s = 1;
    },

    randomDamage: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp1 -= this.randomAttack;
      }
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0) {
        this.hp1 = 0;
        this.image2 = this.win;
        this.image1 = this.lose;
      }

      if (this.hp2 <= 0) {
        this.hp2 = 0;
        this.image2 = this.lose;
        this.image1 = this.win;
      }
    },

    randomDamageSP: function (min, max) {
      this.randomAttack = Math.max(Math.floor(Math.random() * max) + 1, min);
      if (this.hp1 != 0 && this.hp2 != 0) {
        this.hp2 -= this.randomAttack;
      }
      if (this.hp1 <= 0) {
        this.hp1 = 0;
        this.image2 = this.win;
        this.image1 = this.lose;
      }

      if (this.hp2 <= 0) {
        this.hp2 = 0;
        this.image2 = this.lose;
        this.image1 = this.win;
      }
    },
  },
};
</script>

<style>
</style>