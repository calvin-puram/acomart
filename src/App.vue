<template>
  <Main />
</template>

<script>
import Main from "./components/layouts/Main.vue";

export default {
  name: "App",
  components: {
    Main,
  },
};
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  font-size: $body-font-size;
  font-weight: $body-font-weight;
  color: $white;
  background: $dark;
}
</style>
