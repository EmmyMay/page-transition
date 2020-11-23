<template>
  <div class="home">     
  <navi></navi>
  <h1>Cadet Thrill</h1>      
  </div>
</template>

<script>
// @ is an alias to /src
import navi from '@/components/navi.vue';

export default {
  name: 'Home',
  components: {
    navi
  }
}
</script>

<style scoped>
.home{
  height: 100vh;
  background-color: white;

}

h1{
  font-size: 5rem;
  position: relative;
  top: 12rem;
}
</style>
