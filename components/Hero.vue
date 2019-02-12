<template>
  <b-img-lazy :src="source"/>
</template>

<script>
import HeroAttack from "../assets/hero/hero-attack.gif";
import HeroIdle from "../assets/hero/hero-idle.gif";
import HeroJump from "../assets/hero/hero-jump.gif";
import HeroRun from "../assets/hero/hero-run.gif";

export default {
  name: "hero",
  data: function() {
    switch (this.sprite) {
      case "idle":
        return {
          source: HeroIdle
        };
      case "attack":
        return {
          source: HeroAttack
        };
      case "jump":
        return {
          source: HeroJump
        };
      case "idle":
        return {
          source: HeroRun
        };
      default:
        return {
          source: HeroIdle
        };
    }
  },
  props: ["sprite"]
};
</script>