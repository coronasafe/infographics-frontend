<template>
  <div>
    <v-container fluid>
      <v-row>
        <v-col cols="12" lg="3" md="3" sm="6" class="ml-5">
          <v-card class="ml-8">
            <v-carousel cycle height="400" hide-delimiter-background show-arrows-on-hover>
              <div v-for="(data, i) in result.infographics_images" :key="i">
                <v-carousel-item :src="data.image.url"></v-carousel-item>
              </div>
            </v-carousel>

            <v-card-title>{{result.title}}</v-card-title>
            <v-card-text>{{result.Description}}</v-card-text>
            
            <v-card-actions>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'facebook']" class="icon"/>
              </v-btn>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'twitter']" class="icon" />
              </v-btn>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'whatsapp']" class="icon" />
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      result: []
    };
  },
  methods: {
    getData() {
      let rel = this.$route.params.id;
      this.$axios({
        url: `https://manager.raksha.life/infographics/${rel}`,
        method: "GET"
      })
        .then(res => {
          this.result = res.data;
          console.log(result.infographics_images[0].image.url)
        })
        .catch(e => {
          console.log(e.response.data);
        });
    }
  },
  beforeMount() {
    this.getData();
  }
};
</script>


<style scoped>
.icon{
  font-size: 20px;
}
</style>