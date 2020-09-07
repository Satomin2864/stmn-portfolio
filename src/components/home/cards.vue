<template>
  <v-container fluid fill-height>
    <v-row style="height: 100px;" justify="center">
      <h1>topic</h1>
    </v-row>
    <v-row style="height: 100px;" justify="center" align-content="center">
      <v-col cols="3" v-for="n in 3" :key="n">
        <v-card color="blue" outlined tile height="150"></v-card>
      </v-col>
    </v-row>
    <v-row style="height: 200px;" justify="center" align-content="center">
      <v-card class="mx-auto grey lighten-2" max-width="344" outlined>
        <h2>more...</h2>
      </v-card>
    </v-row>
  </v-container>
</template>
<script>
export default {};
</script>