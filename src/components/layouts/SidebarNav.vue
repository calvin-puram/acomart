<template>
  <div class="sidebarnav__wrapper">
    <div v-for="(navItem, i) in nav" :key="i">
      <div class="sidebarnav">
        <i :class="navItem.icon"></i>
        <div class="sidebarnav__navcontent">{{ navItem.name }}</div>
      </div>
    </div>
    <div class="sidebarnav__divider"></div>
    <div class="sidebarnav">
      <i class="fas fa-cog sidebarnav__icon"></i>
      <div class="sidebarnav__navcontent">Settings</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    nav: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.sidebarnav__wrapper {
  padding-top: 1.5rem;
}
.sidebarnav {
  display: flex;
  align-items: center;
  padding: 1rem 0;
  color: $gray;
  width: 80%;
  cursor: pointer;
  transition: all 0.5s ease-in-out;

  &:hover {
    color: $red;
  }

  &__icon {
    padding-right: 1.6rem;
  }

  &__navcontent {
    color: $gray-light;
  }

  &__divider {
    height: 0.1rem;
    background: $gray-light;
    margin: 1rem 0;
  }
}

@include laptop {
  .sidebarnav__wrapper {
    padding-top: 0.8rem;
  }
  .sidebarnav {
    width: 100%;

    &__icon {
      padding-right: 0;
      font-size: $h-2-font-size;
      text-align: center;
      padding: 0 0.2rem;
    }

    &__navcontent {
      display: none;
    }
  }
}
</style>
