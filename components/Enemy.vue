<template>
  <b-img-lazy :src="sprite"/>
</template>
<script>
import Ghost from "../assets/ghost/ghost.gif";
export default {
  name: "enemy",
  props: {
    which: {
      type: String,
      required: true
    }
  },
  data: function() {
    let sprite = Ghost;
    if (this.which === "ghost") {
      sprite = Ghost;
    }
    return {
      sprite
    };
  }
};
</script>
