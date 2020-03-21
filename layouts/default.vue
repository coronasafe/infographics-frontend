<template>
  <div>
    <v-app>
    <appBar />
    <v-content>
    <nuxt />
  </v-content>
    </v-app>
  </div>
</template>

<script>
import appBar from '../components/appBar'
export default {
   components:{
   appBar,
 }
}
</script>

<style>

</style>
