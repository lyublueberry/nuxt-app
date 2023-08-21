<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <nuxt-link active-class="active" exact class="nav-link" to="/">
            Home
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/about">
            About Me
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/users">
            Users
          </nuxt-link>
        </li>
        <li v-if="!hasToken" class="nav-item">
          <nuxt-link class="nav-link" to="/login">
            Login
          </nuxt-link>
        </li>
        <li v-else class="nav-item">
          <a @click.prevent="logout" class="nav-link" href="#">
            Logout
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>
<script>
export default {
  computed:{
    hasToken(){
      this.$store.getters.hasToken;
    }
  },
  methods: {
    logout(){
      this.$store.dispatch('logout');
      this.$router.push('/login');
    }
  },
}
</script>
