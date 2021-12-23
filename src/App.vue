<template>
  <div id="app">
    <h1>Promoters.com</h1>
  </div>
</template>

<script>

export default {

  name: 'App',
  data() {
    return {
      token: "1|sX8SjZxrk0Pnj0cZMJvtMhbELPptIDf5bJL5XapW",
      name: "brand three"
    }
  },
  mounted () {
    let data = new FormData();
    data.append("name", this.name)
    // this.axios.get("http://promoters.owl/api/brands" , { headers: {"Authorization" : `Bearer ${this.token}`} })
    //           .then(response => (console.log(response)));
    this.axios.post("http://promoters.owl/api/brands/store" , data
              , { headers: {"Authorization" : `Bearer ${this.token}`} })
              .then(response => (console.log(response)));

    // this.axios.post("http://promoters.owl/api/login" , { 
    //   "email": "Client@gmail.com",
    //   "password": "01200902377"
    //  }).then(response => (console.log(response)));
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
