<template>
  <div class="main">
    <Sidebar />
    <MainPage />
  </div>
</template>

<script>
import MainPage from "../sections/Mainpage.vue";
import Sidebar from "../sections/Sidebar.vue";

export default {
  name: "Main",
  components: {
    MainPage,
    Sidebar,
  },
};
</script>

<style lang="scss">
.main {
  display: flex;
  min-height: 100vh;
}
</style>
