<template>
  <div class="container">
    <div id="navbar" class="d-flex justify-content-start">
      <div class="navbar-links">
        <nuxt-link to="/" activeClass="active">Home</nuxt-link>
        <nuxt-link to="/videos" activeClass="active">Videos</nuxt-link>
        <nuxt-link to="/theatre" activeClass="active">Theatre</nuxt-link>
      </div>
    </div>
    <div id="theatre-body">
      <nuxt/>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>
  #theatre-body {
    background-color: black;
    color: white;
  }
  .navbar-links > a {
    margin: 0 10px 0 10px;
    padding: 20px;
    text-decoration: none;
  }
  a:hover{
    background-color: rgb(117, 46, 46);
    color: white;
  }
  .active{
    color: red;
  }
</style>