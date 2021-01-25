<template>
  <section class="home">
    <HomeHero />
    <!-- <Cards /> -->
  </section>
</template>
<script>
import HomeHero from "./HomeHero.vue";
// import Cards from "./cards.vue";

export default {
  components: {
    HomeHero
  }
};
</script>
<style lang="scss" scoped>
.home {
  padding-bottom: 0px;
}
</style>