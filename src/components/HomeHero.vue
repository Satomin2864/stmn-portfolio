<template>
  <!-- <section class="home-hero"> -->
  <!-- <v-container fluid fill-height class="home-hero__content"> -->
  <v-container fluid fill-height>
    <v-row>
      <v-img src="../assets/top.png">
        <v-overlay :absolute="true" :value="true">
          <v-col class="home-hero__text">
            <p>Welcom to my website.</p>
            <p>I'm an enginner.</p>
          </v-col>
        </v-overlay>
      </v-img>
    </v-row>
  </v-container>
  <!-- </section> -->
</template>

<style  lang="scss" scoped>
.home-hero__content {
  width: 100%;
  height: 50vh;
  z-index: 1;
  //   &::before {
  //     content: " ";
  //     background-color: rgba(0, 0, 0, 0.5);
  //     position: absolute;
  //     top: 0;
  //     right: 0;
  //     bottom: 0;
  //     left: 0;
  //     z-index: 2;
  //   }
}
.home-hero__text {
  color: rgb(245, 248, 245);
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  z-index: 3;
}
</style>