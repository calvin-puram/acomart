<template>
  <div class="sidebar">
    <div class="sidebar__main">
      <div class="sidebar__logo">
        <img
          class="sidebar__logo-main"
          src="../../assets/img/logo.png"
          alt="logo"
        />
      </div>

      <div class="sidebar__nav">
        <SidebarNav :nav="nav" />
      </div>
    </div>
  </div>
</template>

<script>
import SidebarNav from "../layouts/SidebarNav.vue";
export default {
  name: "Sidebar",
  components: {
    SidebarNav,
  },
  setup() {
    const nav = [
      { name: "Movies", icon: "fas fa-film sidebarnav__icon" },
      { name: "Series", icon: "fas fa-ticket-alt sidebarnav__icon" },
      {
        name: "Downloads",
        icon: "fas fa-cloud-download-alt sidebarnav__icon",
      },
      { name: "My List", icon: "fas fa-play sidebarnav__icon" },
      { name: "Afrocinema", icon: "fas fa-compact-disc sidebarnav__icon" },
    ];

    return {
      nav,
    };
  },
};
</script>

<style lang="scss" scoped>
.sidebar {
  min-height: 100vh;
  margin-bottom: 2rem;
  width: 15%;
  padding-left: 0.8rem;
  padding-top: 3rem;
  background: rgb(33, 22, 6);
  background: linear-gradient(
    29deg,
    rgb(51, 34, 9),
    rgb(5, 5, 5) 40%,
    rgba(3, 3, 3, 1) 30%
  );

  &__main {
    width: 70%;
    margin: auto;
  }

  &__logo {
    width: 100%;

    &-main {
      width: 100%;
      object-fit: contain;
    }
  }
}

@include laptop {
  .sidebar {
    width: 5%;
    padding-left: 0rem;
    margin: 0 auto;
    padding-top: 3rem;
  }
}

@include mobile {
  .sidebar {
    display: none;
  }
}
</style>
