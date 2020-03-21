<template>
  <v-content >
    
    <v-container>

        <v-row>

              <v-col cols="12" lg="3" md="4" sm="6" v-for="i in 12" :key="i">
                
                
                
                <nuxt-link to="/1234">
                      

                      <v-card>
                        <v-img src="https://raksha-infographics.s3.ap-south-1.amazonaws.com/1ebb2275af2744748e4f06374356e0d0.png" alt="" />
                      </v-card>


                </nuxt-link>

              </v-col>


            </v-row>


    </v-container>
    
    
    
    

  </v-content>
</template>

<script>

export default {
  
}
</script>

<style>

</style>
