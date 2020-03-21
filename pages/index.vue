<template>
  <v-content>
    <v-container>
      <v-row>
        <v-col cols="12" lg="3" md="4" sm="6" v-for="result in results" :key="result.id">
          <v-hover v-slot:default="{ hover }">
            <nuxt-link :to="'/' + result.id">
              <v-card :elevation="hover ? 12 : 2">
                <v-img :src="result.infographics_images[0].image.url" alt />
                <v-card-title>{{result.title}}</v-card-title>
              </v-card>
            </nuxt-link>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </v-content>
</template>

<script>
export default {
  data() {
    return {
      results: []
    };
  },

  mounted() {
    this.$axios({
      url: "https://manager.raksha.life/infographics",
      method: "GET"
    })
      .then(res => {
        //console.log(this.data.results);
        this.results = res.data;
      })
      .catch(err => {
        console.log(err);
      });
  }
};
</script>

<style>
</style>
