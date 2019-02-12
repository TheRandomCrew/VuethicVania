<template>
  <div>
    <button @click="leftPlus" class="button--green">go left</button>
    <button @click="leftMinus" class="button--green">go right</button>
    <button @click="jump" class="button--grey">Jump</button>
    
    <Floor :left="left">
    </Floor>
      <div class="hero">
        <b-img-lazy
          :style="{
            position: 'absolute',
            left: '50%',
            top:top + 'px', 
            fontSize: fontSize + 'px' 
          }"
          :src="sprite"
        />
      </div>
  </div>
</template>

<script>
import Floor from "@/components/Floor";
import HeroAttack from "@/assets/hero/hero-attack.gif";
import HeroIdle from "@/assets/hero/hero-idle.gif";
import HeroJump from "@/assets/hero/hero-jump.gif";
import HeroRun from "@/assets/hero/hero-run.gif";

export default {
  components: {
    Floor
  },
  data: function() {
    return {
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
    leftMinus: function() {
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
<style>
.hero {
  position: "absolute";
  left: "50%";
}
</style>