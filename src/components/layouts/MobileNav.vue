<template>
  <div class="mobile__nav">
    <div id="sidemenu">
      <div class="logo__wrapper">
        <img class="logo-mobile" src="../../assets/img/logo.png" alt="logo" />
      </div>
      <button
        class="sidemenu__btn"
        v-on:click="navOpen = !navOpen"
        v-bind:class="{ active: navOpen }"
      >
        <span class="top"></span>
        <span class="mid"></span>
        <span class="bottom"></span>
      </button>
      <transition name="translateX">
        <nav v-show="navOpen">
          <div class="sidemenu__wrapper">
            <div class="logo__wrapper">
              <img
                class="logo-mobile"
                src="../../assets/img/logo.png"
                alt="logo"
              />
            </div>
            <ul class="sidemenu__list">
              <li class="sidebarnav">
                <i class="fas fa-film sidebarnav__icon"></i>
                <div class="sidebarnav__navcontent-mob">Movies</div>
              </li>
              <li class="sidebarnav">
                <i class="fas fa-ticket-alt sidebarnav__icon"></i>
                <div class="sidebarnav__navcontent-mob">Series</div>
              </li>
              <li class="sidebarnav">
                <i class="fas fa-cloud-download-alt sidebarnav__icon"></i>
                <div class="sidebarnav__navcontent-mob">Downloads</div>
              </li>
              <li class="sidebarnav">
                <i class="fas fa-play sidebarnav__icon"></i>
                <div class="sidebarnav__navcontent-mob">My Lists</div>
              </li>
              <li class="sidebarnav">
                <i class="fas fa-compact-disc sidebarnav__icon"></i>
                <div class="sidebarnav__navcontent-mob">Afrocinema</div>
              </li>
              <div class="sidebarnav__divider"></div>
              <li class="sidebarnav">
                <i class="fas fa-cog sidebarnav__icon"></i>
                <div class="sidebarnav__navcontent-mob">Settings</div>
              </li>
            </ul>
          </div>
        </nav>
      </transition>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const navOpen = ref(false);

    return {
      navOpen,
    };
  },
};
</script>

<style lang="scss" scoped>
#sidemenu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 1rem;

  .logo-mobile {
    width: 120px;
  }
  nav {
    width: 100%;
    background: rgb(33, 22, 6);
    background: linear-gradient(
      29deg,
      rgb(51, 34, 9),
      rgb(5, 5, 5) 40%,
      rgba(3, 3, 3, 1) 30%
    );
    position: fixed;
    top: 0;
    right: 0;
    z-index: 99;
  }

  .sidemenu {
    &__btn {
      display: block;
      width: 50px;
      height: 50px;
      background: transparent;
      border: none;
      position: relative;
      z-index: 100;
      appearance: none;
      cursor: pointer;
      outline: none;

      span {
        display: block;
        width: 20px;
        height: 2px;
        margin: auto;
        background: $white;
        position: absolute;
        top: 0;
        bottom: 0;
        color: #333;
        right: 0;
        transition: all 0.4s ease;

        &.top {
          transform: translateY(-8px);
        }

        &.bottom {
          transform: translateY(8px);
        }
      }
      &.active {
        .top {
          transform: rotate(-45deg);
        }
        .mid {
          transform: translateX(-20px) rotate(360deg);
          opacity: 0;
        }
        .bottom {
          transform: rotate(45deg);
        }
      }
    }

    &__wrapper {
      padding-top: 50px;

      .logo__wrapper {
        display: flex;
        width: 100%;
        justify-content: center;
        .logo-mobile {
          width: 120px;
        }
      }
    }

    &__list {
      padding-top: 50px;
      list-style: none;
      padding: 0;
      padding-top: 1rem;
      margin: 0;

      .sidebarnav {
        display: flex;
        align-items: center;
        padding: 1rem 0;
        color: $white;
        width: 80%;
        cursor: pointer;
        padding-left: 1rem;
        transition: all 0.5s ease-in-out;

        &:hover {
          color: $red;
        }

        &__icon {
          padding-right: 1.6rem;
          font-size: 1.2rem;
        }

        &__navcontent-mob {
          color: $white;
        }

        &__divider {
          height: 0.1rem;
          background: $gray-light;
          margin-top: 1rem;
        }
      }
    }

    &__item {
      a {
        text-decoration: none;
        line-height: 1.6em;
        font-size: 1.6em;
        padding: 0.5em;
        display: block;
        color: white;
        transition: 0.4s ease;

        &:hover {
          background: lightgrey;
          color: dimgrey;
        }
      }
    }
  }
}

.translateX-enter {
  transform: translateX(-200px);
  opacity: 0;
}

.translateX-enter-active,
.translateX-leave-active {
  transform-origin: top left 0;
  transition: 0.2s ease;
}

.translateX-leave-to {
  transform: translateX(-200px);
  opacity: 0;
}
</style>
