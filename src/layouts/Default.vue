<template>
  <div class="body-container">
    <header class="header">
      <strong>
        <g-link to="/">
          <g-image
            alt="Vlad's Portfolio"
            src="~/imgs/logo-hex.svg"
            width="55"
          />
        </g-link>
      </strong>

      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
        <g-link class="nav__link" to="/contact/">Contact</g-link>
      </nav>
    </header>
    <slot />
    <footer>
      <v-card flat class="text-center">
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon"
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-text>
        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} © <strong>Vlad Mihalca</strong>
        </v-card-text>
      </v-card>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style lang="scss">
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}

.body-container {
  max-width: 1280px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
footer {
  text-align: center;
  justify-content: center;
  background: white;
  .v-card {
    width: 100%;
  }
}
</style>

<script>
export default {
  data: () => ({
    icons: ["mdi-facebook", "mdi-linkedin"],
  }),
};
</script>
