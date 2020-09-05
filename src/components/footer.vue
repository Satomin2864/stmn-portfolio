<template>
  <v-footer padless>
    <v-card class="flex" flat tile>
      <v-card-actions class="teal darken-2 justify-center">
        &copy;{{ new Date().getFullYear() }} —
        <strong>stmn</strong>
      </v-card-actions>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({})
};
</script>