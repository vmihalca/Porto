<template>
  <v-footer>
    <v-card flat tile class="text-center">
      <v-card-text>
        <v-btn v-for="icon in icons" :key="icon" class="mx-4 white--text" icon>
          <v-icon large color="green darken-2">
            mdi-domain
          </v-icon>
        </v-btn>
      </v-card-text>
      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} © <strong>Vlad Mihalca</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<style></style>

<script>
export default {
  metaInfo: {
    title: "Footer",
  },
};
</script>
