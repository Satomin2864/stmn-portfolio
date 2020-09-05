<template>
  <v-app id="inspire">
    <Header />
    <router-view />
    <Footer />
  </v-app>
</template>

<script>
import Header from "./components/header";
import Footer from "./components/footer";

export default {
  props: {
    source: String
  },
  data: () => ({
    drawer: null
  }),
  components: {
    Header,
    Footer
  }
};
</script>