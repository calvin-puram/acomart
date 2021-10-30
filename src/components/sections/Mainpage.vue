<template>
  <div class="mainpage">
    <div class="mainpage__hero">
      <div class="mainpage__heroview">
        <div class="mainpage__heroview-back">
          <i class="fas fa-chevron-left"></i>
          <span class="back">Back</span>
        </div>

        <div class="mainpage__heroview-content">
          <div class="mainpage__heroview-img">
            <img
              src="../../assets/img/bg-sm.jpg"
              alt="movie cover"
              class="mainpage__heroview-imgmain"
            />
          </div>

          <div class="mainpage__heroview-cont">
            <h1 class="mainpage__heroview-cont-head">Stranger Things</h1>
            <ul class="movie__details">
              <li class="movie__details-list">
                <span class="movie__details-text">Thriller</span>
                <span class="dot"></span>
              </li>
              <li class="movie__details-list">
                <span class="movie__details-text">2019</span>
                <span class="dot"></span>
              </li>
              <li class="movie__details-text">1hr24min</li>
            </ul>
            <div class="ratings">
              <i class="fas fa-star star-bg"></i>
              <i class="fas fa-star star-bg"></i>
              <i class="fas fa-star star-bg"></i>
              <i class="fas fa-star star-bg"></i>
              <i class="far fa-star star-bg-none"></i>
            </div>
            <button class="rate__movie">
              <span>Rate this movie</span>
              <i class="fas fa-chevron-right"></i>
            </button>
          </div>
        </div>

        <div class="mainpage__heroview-actions">
          <button class="rate__movie-play">
            <i class="fas fa-play"></i>
            <span class="btn-text">Watch now</span>
          </button>

          <button class="rate__movie-bookmark">
            <i class="fas fa-bookmark"></i>
            <span>Added to my list</span>
          </button>

          <button class="rate__movie-remove">
            <i class="fas fa-minus-circle"></i>
            <span>Rate this movie</span>
          </button>
        </div>
      </div>
    </div>

    <div class="mainpage__content">
      <div class="mainpage__pagination">
        <h2 class="mainpage__pagination-header">Seasons</h2>
        <div
          class="mainpage__pagination-main"
          v-for="i in [1, 2, 3, 4, 5, 6, 7]"
          :key="i"
        >
          <Paginate :num="i" />
        </div>
      </div>

      <div class="mainpage__movies">
        <Movies />
      </div>
    </div>
  </div>
</template>

<script>
import Movies from "../layouts/Movies.vue";
import Paginate from "../layouts/Paginate.vue";
export default {
  name: "MainPage",
  components: {
    Movies,
    Paginate,
  },
};
</script>

<style lang="scss">
.mainpage {
  width: 85%;
  background: $dark;

  &__hero {
    background: linear-gradient(45deg, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.8)),
      url("../../assets/img/bg.jpg") no-repeat center center;
    background-size: cover;
    width: 95%;
    height: 25rem;
    margin: 3rem auto;
  }

  &__heroview {
    display: flex;
    flex-direction: column;
    width: 80%;
    margin: auto;
    padding: 2.4rem 0;

    &-back {
      color: $white;
      display: flex;
      align-items: center;
      padding: 1rem 0;
      cursor: pointer;

      .back {
        margin-left: 0.8rem;
      }
    }

    &-content {
      display: flex;
      margin-top: 1rem;
      margin-bottom: 1.5rem;
      .mainpage__heroview-img {
        img {
          width: 120px;
        }
      }

      .mainpage__heroview-cont {
        margin-left: 2rem;

        &-head {
          color: $white;
          padding-top: 0.6rem;
          padding-bottom: 0.8rem;
          font-weight: $h-1-font-weight;
          font-size: 2.4rem;
        }

        .movie__details {
          display: flex;
          align-items: center;
          list-style: none;
          padding-bottom: 0.8rem;

          &-text {
            font-size: $h-6-font-size;
            color: $gray;
          }
        }

        .ratings {
          display: flex;
          align-items: center;
          .fa-star {
            margin-right: 1rem;
          }
          .star-bg {
            color: goldenrod;
          }
          .star-bg-none {
            color: $white;
          }
        }

        // buttons
        .rate__movie {
          display: flex;
          align-items: center;
          justify-content: space-between;
          color: $white;
          border-radius: 30px;
          border: $red;
          padding: 0.5rem 2rem;
          background: $red;
          margin-top: 1.3rem;
          transition: all 0.5s ease-in-out;

          &:hover {
            background: darken($red, 50%);
          }

          .fa-chevron-right {
            padding-left: 0.5rem;
          }
        }
      }

      .mainpage__heroview-actions {
        display: flex;
        align-items: center;

        // buttons
      }
    }

    .dot {
      height: 0.4rem;
      width: 0.4rem;
      background-color: $white;
      border-radius: 50%;
      display: inline-block;
      margin: 0.6rem 0.8rem;
    }

    .movie__details {
      &-list {
        display: flex;
        align-items: center;
      }

      &-text {
        color: $white;
        padding-right: 0.4rem;
      }
    }
  }

  &__content {
    width: 90%;
    margin: 1rem auto;
  }

  &__pagination {
    display: flex;
    align-items: center;

    &-header {
      font-size: $h-2-font-size;
      margin-right: 1rem;
      font-weight: $h-2-font-weight;
    }

    &-main {
      margin-left: 1rem;
      display: flex;
      align-items: center;
    }
  }
  //buttons
  .rate__movie-play {
    @include btn($red, $white);
  }

  .rate__movie-bookmark {
    @include btn($white, #333);
  }

  .rate__movie-remove {
    display: inline-block;
    color: $white;
    border-radius: 30px;
    border: 1px solid $white;
    padding: 0.4rem 1.6rem;
    background: transparent;
    margin-right: 0.8rem;
    cursor: pointer;
    transition: all 0.5s ease-in-out;

    &:hover {
      border: 1px solid $red;
    }

    span {
      padding-left: 0.5rem;
    }
  }
}
</style>
