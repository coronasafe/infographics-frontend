<template>
  <div>



    <v-container class="mt-5">
      
      
      <v-row>


        <v-col cols="12" lg="8" md="12" sm="12"  class=" ">
          
          
          
          <v-card >
            <v-carousel cycle height="400" hide-delimiter-background show-arrows-on-hover>
              
              
              <div v-for="(data, i) in result.infographics_images" :key="i">
                <v-carousel-item :src="data.image.url"></v-carousel-item>
              </div>

            </v-carousel>
          </v-card>

            
            
            



        </v-col>

        <v-col cols="12" lg="4" md="12" sm="12" class=" " >

          
          <div class="d-flex flex-column ">

            

            <span class="display-3 ">
              {{result.title}}
            </span>

            
            <div class="d-flex flex-wrap my-3">

              <div v-for="i in 8" :key="i" dense dark class="black metaTag white--text overline px-3 py-1 mr-1 my-1">
                  lorem
                  </div>

            </div>

            

            <span class="subtitle-2">
              {{result.Description}} Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut a fermentum velit. Sed eget congue turpis, id lacinia nunc. Etiam venenatis facilisis nunc non dapibus. Vestibulum odio mauris, congue et purus in, sagittis blandit quam. Vivamus vitae condimentum mi. Nullam id orci a ipsum venenatis interdum. Suspendisse porta, magna ac congue interdum, ante nibh commodo arcu, nec fermentum risus tellus nec est. Ut rutrum sollicitudin erat, sit amet egestas sapien dictum eget. Nam ullamcorper, tellus id vestibulum vestibulum, leo velit rutrum leo, sit amet suscipit massa dui vel nisl
            </span>
              

              <div class="d-fex justify-space-between align-center">
                <v-btn icon>
                <font-awesome-icon :icon="['fab', 'facebook']" class="icon"/>
              </v-btn>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'twitter']" class="icon" />
              </v-btn>
              <v-btn icon>
                <font-awesome-icon :icon="['fab', 'whatsapp']" class="icon" />
              </v-btn>
              </div>
            

          </div>



        </v-col>
      </v-row>


    </v-container>

    <v-col>



    </v-col>



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
.metaTag{
  border-radius:.4em;
}
</style>