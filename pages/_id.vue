<template>
  <div>
    <v-container fluid>
      <v-card class="mx-auto">
        <v-img
          class="white--text align-end"
          height="200px"
          src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
        />
        <v-card-title>{{result.title}}</v-card-title>
        <v-card-text>Lorem ispum dolor</v-card-text>
        <v-card-actions>
          <v-btn icon>
            <font-awesome-icon :icon="['fab', 'facebook']" class="large"/>
          </v-btn>
          <v-btn icon>
            <font-awesome-icon :icon="['fab', 'twitter']" class="large"/>
          </v-btn>
          <v-btn icon>
            <font-awesome-icon :icon="['fab', 'whatsapp']" class="large"/>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  data(){
      return{
          result:[]
      }
  },
  methods: {
    getData() {
      //alert('hello')
      this.$axios.$get({
          url:`https://manager.raksha.life/infographics/5e7460b30b80f8076a5c22d4`
      })
      .then((res)=>{
          this.result = res.data
          console.log(this.result)
      })
      .catch((e)=>{
          console.log(e.response.data)
      })
      ;
    }
  },
  mounted(){
      this.getData()

  }
};
</script>