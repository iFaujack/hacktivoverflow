<template>
  <div id="app" class="bg-color">
    <Navbar></Navbar>
    <b-container fluid>
      <router-view />
    </b-container>
  </div>
</template>

<script>
import { mapState } from 'vuex';
import Navbar from '@/components/Navbar.vue';

export default {
  computed: mapState(['isLogin']),
  components: {
    Navbar,
  },
  created() {
    if (localStorage.token) {
      this.$store.commit('SAVELOGIN');
    }
  },
};
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}
.bg-color {
  background-color: #eff0f1;
  min-height: 100vh;
}
#nav a.router-link-exact-active {
  color: #42b983;
}
* {
  font-family: 'Montserrat', sans-serif;
}
</style>
