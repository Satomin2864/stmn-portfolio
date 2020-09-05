<template>
  <v-app-bar app dense class="px-0">
    <v-toolbar-items>
      <v-btn text to="/">
        <v-icon>mdi-home</v-icon>
      </v-btn>
    </v-toolbar-items>
    <v-spacer />
    <v-toolbar-items>
      <v-btn text to="/about">
        <v-icon>mdi-account-circle</v-icon>
      </v-btn>
      <v-btn text to="/skills">
        <v-icon>mdi-dns</v-icon>
      </v-btn>
      <v-btn text to="/links">
        <v-icon>mdi-link-variant</v-icon>
      </v-btn>
    </v-toolbar-items>
    <div class="px-3">
      <v-switch dense color="gray" v-model="$vuetify.theme.dark" hide-details>
        <template v-slot:label>
          <v-icon class="pl-3">{{ $vuetify.theme.dark ? 'fas fa-moon' : 'fas fa-sun' }}</v-icon>
        </template>
      </v-switch>
    </div>
  </v-app-bar>
</template>

<script>
export default {
  data: vm => ({
    initialDark: vm.$vuetify ? vm.$vuetify.theme.dark : false
  }),

  beforeDestroy() {
    if (!this.$vuetify) return;
    this.$vuetify.theme.dark = this.initialDark;
  }
};
</script>