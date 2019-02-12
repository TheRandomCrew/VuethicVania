<template>
  <div :style="[styles, stylesStatic]">
  </div>
</template>
<script>
import FloorBG from "@/assets/Environment/graveyard.png";
export default {
  name: "floor",
  data: function() {
    return {
      floor: FloorBG,
      stylesStatic: {
        position: "absolute",
        "background-position": "center",
        "background-repeat": "repeat",
        "background-size": "cover",
        height: "400px",
        width: "100%",
        top: "100px"
      }
    };
  },
  props:{
      left:{
          type:Number,
          required:true
      },
      facing:{
          type:Number,
          required:true
      }
  },
  computed: {
    styles() {
      return {
        backgroundImage: "url(" + this.floor + ")",
        left: this.left + "px"
      }
    }
  }
};
</script>

<style>
</style>