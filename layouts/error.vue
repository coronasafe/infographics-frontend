<template>
  <div>
    error
  </div>
</template>

<script>
export default {
  
  data () {
    return {
      
    }
  },
  head () {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  }
}
</script>

<style scoped>

</style>
