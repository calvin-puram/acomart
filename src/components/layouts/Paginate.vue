<template>
  <div v-on:click="filter(num)" class="box" :class="{ active: isActive }">
    {{ num }}
  </div>
</template>

<script>
export default {
  props: {
    num: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      isActive: false,
      nums: 1,
    };
  },
  methods: {
    filter(num) {
      if (num === this.num) {
        this.isActive = !this.isActive;
      }
    },
  },
  mounted() {
    if (this.num === 1) {
      this.isActive = !this.isActive;
    }
  },
};
</script>
<style lang="scss">
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
</style>
