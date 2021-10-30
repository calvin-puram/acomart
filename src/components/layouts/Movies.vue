<template>
  <div class="movie__wrapper">
    <div>
      <div class="movie movie-1" v-for="i in [1, 2, 3, 4, 5]" :key="i">
        <div class="movie__name">
          <span class="movie__num">{{ i }}</span>
          <div class="movie__name-main">
            <p class="main_header-primary">Episode {{ i }}</p>
            <p class="main_header-secondary">1hr24min</p>
          </div>
        </div>

        <div class="movie__action">
          <i class="fas fa-cloud-download-alt movie__icons"></i>
          <i class="far fa-play-circle movie__icons"></i>
        </div>
      </div>
    </div>

    <div>
      <div class="movie movie-2" v-for="i in [6, 7, 8, 9, 10]" :key="i">
        <div class="movie__name">
          <span class="movie__num">{{ i }}</span>
          <div class="movie__name-main">
            <p class="main_header-primary">Episode {{ i }}</p>
            <p class="main_header-secondary">1hr24min</p>
          </div>
        </div>

        <div class="movie__action">
          <i class="fas fa-cloud-download-alt movie__icons"></i>
          <i class="far fa-play-circle movie__icons"></i>
        </div>
      </div>
    </div>

    <div>
      <div class="movie movie-3" v-for="i in [11, 12, 13, 14, 15]" :key="i">
        <div class="movie__name">
          <span class="movie__num">{{ i }}</span>
          <div class="movie__name-main">
            <p class="main_header-primary">Episode {{ i }}</p>
            <p class="main_header-secondary">1hr24min</p>
          </div>
        </div>

        <div class="movie__action mobile">
          <i class="fas fa-cloud-download-alt movie__icons"></i>
          <i class="far fa-play-circle movie__icons"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.movie__wrapper {
  display: flex;
  padding-top: 1.5rem;
  width: 100%;
  align-items: center;
  justify-content: space-between;
}

.movie {
  padding-bottom: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;

  .mobile {
    display: none;
  }

  &__action {
    margin-left: 10rem;
    display: flex;
  }

  &__icons {
    color: $white;
    cursor: pointer;
    padding: 0 0.6rem;
    font-size: $h-3-font-size;
    transition: all 0.5s ease-in-out;
    &:hover {
      color: $red;
    }
  }

  &__num {
    font-size: $h-3-font-size;
    color: $white;
    margin-right: 0.5rem;
  }

  &__name {
    display: flex;
    align-items: center;

    &-main {
      padding-left: 0.8rem;
    }

    .main_header-primary {
      font-size: $h-3-font-size;
      font-weight: $h-1-font-weight;
      color: $white;
      padding-bottom: 0.3rem;
      width: auto;
    }

    .main_header-secondary {
      font-size: $h-5-font-size;
      color: $gray;
    }
  }
}

@include laptop {
  .movie__wrapper {
    display: block;
    width: 100%;
    flex-direction: column;
  }
  .movie {
    &__action {
      margin-left: 0;
      display: flex;
    }

    .mobile {
      display: flex;
    }
  }
}

@include mobile {
  .movie {
    .main_header-primary {
      font-size: 0.8rem;
    }
  }
}
</style>
