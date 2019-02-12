<template>
  <div
    class="floor"
    v-bind:style="{ 
        position: 'absolute',
  'background-position': 'center',
  'background-repeat': 'repeat',
  'background-size': 'cover',
  height: '400px',
  width: '100%',
  top: '100px',      
      backgroundImage: 'url(' + floor + ')',      
      left: left + 'px'
    }"
  >{{thisLeft}}</div>
</template>
<script>
import FloorBG from "@/assets/Environment/graveyard.png";
export default {
  name: "floor",
  data: function() {
    return {
      floor: FloorBG,
      thisLeft: this.left
    };
  },
  props: ["left"]
};
</script>

<style>
.floor {
  position: "absolute";
  background-position: "center";
  background-repeat: "repeat;";
  background-size: "cover";
  height: "400px";
  width: "100%";
  top: "100px";
}
</style>