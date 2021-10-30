<template>
  <div v-on:click="filter(num)" class="box" :class="{ active: isActive }">
    {{ num }}
  </div>
</template>

<script>
import { ref, onMounted } from "vue";

export default {
  props: {
    num: {
      type: Number,
      required: true,
    },
  },
  setup(props) {
    const isActive = ref(false);

    const filter = (num) => {
      if (num === props.num) {
        isActive.value = !isActive.value;
      }
    };

    onMounted(() => {
      if (props.num === 1) {
        isActive.value = !isActive.value;
      }
    });

    return {
      filter,
      isActive,
    };
  },
};
</script>
<style lang="scss" scoped>
.box {
  padding: 0.1rem 0.4rem;
  border: 1px solid $gray;
  border-radius: 50%;
  color: $gray;
  margin: 0 0.1rem;
  cursor: pointer;
  font-size: 0.9rem;
  font-weight: bold;
  transition: all 0.2s ease;
  &:hover {
    background: $white;
    color: #333;
  }
}

.active {
  background: $white;
  color: #333;
}

@include mobile {
  .box {
    padding: 0.2rem 0.4rem;
    border: 1px solid $gray;
    border-radius: 50%;
    color: $gray;
    margin: 0 0.1rem;
    cursor: pointer;
    font-size: 0.5rem;
    font-weight: bold;
    transition: all 0.2s ease;
  }
}
</style>
