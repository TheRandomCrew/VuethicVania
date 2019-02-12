<template>
  <div>
    <div v-bind:style="{ 
      position: 'absolute', 
      backgroundImage: 'url(' + BG + ')',
      backgroundPosition: 'center',  
      backgroundRepeat: 'no-repeat;',
      backgroundSize: 'cover',
      height: '500px',
      width: '100%',
      left: left + 'px', 
      top: '0px', }">
      <Hero />
    </div>
  </div>
</template>

<script>
import Hero from '~/components/Hero.vue';
import BackGround from '~/assets/Environment/background.png'
export default {
  components: {
    Hero
  },
  data: function() {
    return {
      BG:  BackGround,
    };
  },
  methods: {
  }
}
</script>

