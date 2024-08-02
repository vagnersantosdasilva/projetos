<template>
  <div>
  <BarraNavegacao></BarraNavegacao>
  <Home></Home>
</div>
</template>

<script>
import BarraNavegacao from './components/BarraNavegacao.vue';
import Home from './Home.vue';
export default {
  name: 'IndexPage',
  components:{
    BarraNavegacao,
    Home
  },

  data() {
    return {
    
    }
  },
  computed: {

   
  },

  mounted() {
  },

  methods:{}
}
</script>
<style scoped>
@keyframes tiltAnimation {
  from {
    transform: perspective(700px) rotateY(-10deg);
  }

  to {
    transform: perspective(700px) rotateY(-20deg);
  }
}


</style>


