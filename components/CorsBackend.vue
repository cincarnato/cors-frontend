<template>
<div>
  <h1>BACKEND</h1>
  Responses:
  <br>
  Get: {{get}}
  <br>
  Post: {{post}}
  <hr><br>
  <h1>Services</h1>
  Get: {{getServices}}
</div>
</template>

<script>
export default {
  name: "CorsBackend",
  data(){
    return {
      get: null,
      post: null,
      getServices: null,
    }
  },
  mounted() {
    this.fetchBackendGet()
    this.fetchBackendPost()
    this.fetchServiceGet()
  },
  methods: {
    fetchBackendGet(){

      this.$axios.$get('http://backend.int:3500/users').then(
        response => {
          console.log(response)
          this.get = response
        }
      )
    },
    fetchBackendPost(){

      this.$axios.$post('http://backend.int:3500/users').then(
        response => {
          console.log(response)
          this.post = response
        }
      )
    },

    //SERVICES
    fetchServiceGet(){

      this.$axios.$get('http://backend.int:3500/services').then(
        response => {
          console.log(response)
          this.getServices = response
        }
      )
    },
  }
}
</script>

<style scoped>

</style>
