<template>
  <div>
    <v-container fluid>
      <v-row>
        <v-col cols="12" lg="3" md="3" sm="6" class="ml-5">
          <v-card class="ml-8">
            <!-- <v-img :src="result.infographics_images[0].image.url" /> -->

            <v-card-title>{{result.title}}</v-card-title>
            <v-card-text>{{result.Description}}</v-card-text>
            
            <v-card-actions>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'facebook']" />
              </v-btn>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'twitter']" class="large" />
              </v-btn>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'whatsapp']" class="large" />
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