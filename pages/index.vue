<template>
  <div>
    <div class="background1" :style="styles">
      <Hero/>
    </div>
  </div>
</template>

<script>
import Hero from "@/components/Hero.vue";
import BackGround from "@/assets/Environment/background.png";
export default {
  components: {
    Hero
  },
  data: function() {
    return {
      BG: BackGround
    };
  },
  methods: {},
  computed: {
    styles() {
      return {
        "background-image": "url(" + this.BG + ")",
        "background-repeat": "no-repeat",
        "background-size": "cover",
        position: "absolute",
        "background-position": "center",
        "background-repeat": "no-repeat;",
        height: "500px",
        width: "100%"
      };
    }
  }
};
</script>
<style scoped>
</style>
