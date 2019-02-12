<template>
  <div>
    <button @click="attack" class="button--grey">Attack</button>
    <button @click="leftMinus" class="button--green">go right</button>
    <button @click="leftPlus" class="button--green">go left</button>
    <button @click="jump" class="button--grey">Jump</button>
    <Floor :left="left" :facing="facing"></Floor>
    <enemy :style="enemyStyles" :which="which"/>
    <hero :style="[styles,stylesStatic]" :sprite="sprite"/>
  </div>
</template>

<script>
import Floor from "@/components/Floor";
import Hero from "@/components/Hero";
import Enemy from "./Enemy";

export default {
  name: "game",
  components: {
    Floor,
    Hero,
    Enemy
  },
  data: function() {
    return {
      sprite: 'idle',
      fontSize: 30,
      left: 80,
      top: 400,
      facing: 1,
      which: "ghost",
      stylesStatic: {
        position: "absolute",
        left: "50%"
      }
    };
  },
  methods: {
    leftPlus: function() {
      const lastLeft = this.left;
      this.sprite = "run";
      this.left = lastLeft - 10;
      this.facing = 1;
      this.idle();
    },
    leftMinus: function() {
      this.facing = -1;
      const lastLeft = this.left;
      this.left = lastLeft + 10;
      this.sprite = "run";
      this.idle();
    },
    jump: function() {
      this.sprite = "jump";
      this.top = 380;
      this.idle();
    },
    attack: function() {
      this.sprite = 'attack';
      this.idle();
    },
    idle: function() {
      this.intervalid1 = setInterval(() => {
        this.sprite = "idle";
        this.top = 400;
      }, 1000);
    }
  },
  computed: {
    styles() {
      return {
        top: this.top + "px",
        "-webkit-transform": "scaleX(" + this.facing + ")",
        transform: "scaleX(" + this.facing + ")",
        fontSize: this.fontSize + "px"
      };
    },
    enemyStyles() {
      let facing = 1;
      let left = this.left + 50 +"px";
      if (this.left < left) {
        facing = this.facing;
      } else {
        facing = this.facing * -1;
      }
      return {
        "-webkit-transform": "scaleX(" + facing + ")",
        transform: "scaleX(" + facing + ")",
        position: "absolute",
        top: "400px",
        left
      };
    }
  }
};
</script>