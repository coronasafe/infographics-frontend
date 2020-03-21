<template>
  <div>
  <v-app>
    <app-bar/>
  </v-app>
  <v-content>
    <nuxt />
  </v-content>
  </div>
</template>

<script>
import appbar from '../components/appbar'
export default {
components : {
  appbar
}
  
}
</script>

<style>

</style>
