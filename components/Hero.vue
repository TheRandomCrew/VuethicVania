<template>
  <div>
    <button @click="leftPlus">go left</button>
    <button @click="jump">Jump</button>    
    {{left}}
    <div
      v-bind:style="{ 
      position: 'absolute', 
      backgroundImage: 'url(' + floor + ')',
      backgroundPosition: 'center',  
      backgroundRepeat: 'repeat;',
      backgroundSize: 'cover',
      height: '400px',
      width: '100%',
      left: left + 'px', 
      top: '100px', }"
    />
    <div class="hero">
        <b-img-lazy
          v-bind:style="{ 
      position: 'absolute', 
      left: '50%', 
      top:top + 'px', 
      fontSize: fontSize + 'px' 
      }"
          v-bind:src="sprite"
        />
      </div>
  </div>
</template>

<script>
import Floor from "../assets/Environment/graveyard.png";
import HeroAttack from "../assets/hero/hero-attack.gif";
import HeroIdle from "../assets/hero/hero-idle.gif";
import HeroJump from "../assets/hero/hero-jump.gif";
import HeroRun from "../assets/hero/hero-run.gif";

export default {
  data: function() {
    return {
      floor: Floor,
      sprite: HeroIdle,
      fontSize: 30,
      left: 80,
      top: 400
    };
  },
  methods: {
    leftPlus: function() {
      const lastLeft = this.left;
      this.sprite = HeroRun;
      this.left = lastLeft - 10;
      const self = this;
      this.idle();
    },
    rightPlus: function() {
      const lastLeft = this.left;
      this.left = lastLeft + 10;
      this.idle();
    },
    jump: function() {
      this.sprite = HeroJump;
      this.top = 380;
      this.idle();
    },
    attack: function() {
      this.sprite = HeroJump;
      this.idle();
    },
    idle: function() {
      this.intervalid1 = setInterval(() => {
        this.sprite = HeroIdle;
        this.top = 400;
      }, 1000);
    }
  }
};
</script>