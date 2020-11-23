<template>
  <div class="about">
    <navi></navi>
    <div class="khaki">
    <h1>Khaki Delight</h1>
    </div>
  </div>
</template>

<script>
import navi from '@/components/navi.vue';
export default {
  components: {
    navi
  }
}
</script>

<style scoped>
.about{
  height: 100vh;
  background-color: khaki;
  display: flex;
  justify-content: center;
}
.khaki{
 align-self: center;
}
h1{
  font-size: 5rem;
}

</style>
