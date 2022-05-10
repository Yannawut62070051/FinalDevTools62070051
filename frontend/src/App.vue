<template>
  <div id="app">
    <MemberVue></MemberVue>
  </div>
</template>

<script>
import MemberVue from "./components/Member.vue";
export default {
  name: "App",
  components: {
    MemberVue,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
}
</style>
