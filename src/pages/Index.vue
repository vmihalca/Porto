<template>
  <Layout>
    <div class="hero-text">
      <h1>Hey there! I'm Vlad. Nice to meet you.</h1>
      <p>A human-centered UX design from Research to User</p>
    </div>

    <section class="projects-section">
      <div
        class="project-card"
        v-for="project in projects"
        :key="project.name"
        :class="project.css"
      >
        <v-row no-gutters>
          <v-col cols="12" sm="12" md="6">
            <v-img :src="project.src"></v-img>
          </v-col>
          <v-col cols="12" sm="12" md="6" class="text-col">
            <div class="card-text">
              <h1>{{ project.name }}</h1>
              <p>{{ project.description }}</p>
              <v-card-actions>
                <v-btn outlined>
                  Read Case Study
                </v-btn>
              </v-card-actions>
            </div>
          </v-col>
        </v-row>
      </div>
    </section>
  </Layout>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          css: "nutri-card",
          bkcolor: "#D1FFD7",
          name: "NutriKid",
          description:
            "NutriKid is a cross-platform service that help kids learn about nutrition. It's goal is to make the learning fun and attractive for children.",
          src: require("~/imgs/nutri-min.jpg"),
        },
        {
          css: "invest-card",
          bkcolor: "",
          name: "Easy Invest",
          description:
            "A highly adaptable and simplified solution that helps those who are new to investing in stock market.",
          src: require("~/imgs/invest.jpg"),
        },
        {
          css: "recet-card",
          bkcolor: "",
          name: "Recetarium",
          description:
            "Retetarium is an app that will help Chefs and cooking enthusiasts to create, save as favorite, organize and search for their favorite recipes.",
          src: require("~/imgs/recetar.jpg"),
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.home-links a {
  margin-right: 1rem;
}
.hero-text {
  text-align: center;
  margin: 5rem 0;
  height: 150px;
}
.projects-section .project-card:nth-child(even) .row {
  flex-direction: row-reverse;
}
.nutri-card {
  background: rgb(209, 255, 215);
  background: linear-gradient(
    180deg,
    rgba(209, 255, 215, 1) 0%,
    rgba(209, 255, 215, 1) 35%,
    rgba(231, 225, 113, 1) 100%
  );
}
.invest-card {
  background: #ccd5cb;
}
.recet-card {
  background: rgb(130, 222, 210);
  background: linear-gradient(
    171deg,
    rgba(130, 222, 210, 1) 24%,
    rgba(231, 225, 113, 1) 100%
  );
}
.project-card {
  margin-bottom: 30px;
  .text-col {
    display: flex;
  }
  .card-text {
    max-width: 400px;
    margin: auto;
    p {
      margin: 20px 0;
      color: #333;
    }
  }
  .v-card__actions {
    padding-left: 0;
  }
}
</style>
