<template>
  <div>
    <div :style="[styles,stylesStatic]">
      <game/>
    </div>
  </div>
</template>

<script>
import Game from "@/components/Game";
import BackGround from "@/assets/Environment/background.png";
export default {
  components: {
    Game
  },
  data: function() {
    return {
      BG: BackGround,
      stylesStatic:{
        "background-repeat": "no-repeat",
        "background-size": "cover",
        "background-position": "center",
        "background-repeat": "no-repeat;",
        position: "absolute",
        height: "500px",
        width: "100%"
      }
    };
  },
  methods: {},
  computed: {
    styles() {
      return {
        "background-image": "url(" + this.BG + ")",        
      };
    }
  }
};
</script>
<style scoped>
</style>
