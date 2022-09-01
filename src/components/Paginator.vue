<template>
    <div class="paginator-container">
    <div class="round-ball red" @click="previous()">
        <i class="fa-solid fa-chevron-left"></i>
    </div>
    <div class="round-ball yellow">
      {{ page }}
    </div>
    <div class="round-ball green" @click="next()">
        <i class="fa-solid fa-chevron-right"></i>
    </div>
  </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue'
  
  export default defineComponent({
  emits: ["previousPage", "nextPage"],
  methods: {
    next() {
      this.$emit("nextPage");
    },
    previous() {
      this.$emit("previousPage");
    },
  },
  props: {
    page: {
      required: true,
      type: Number,
    },
  },
  setup() {
    return {};
  },
});
  </script>
  
  <style lang="scss" scoped>
    .paginator-container {
      width: 100%;
      display: flex;
      justify-content: center;
      margin: 16px 0;
      font-size: 20px;
      gap: 1rem;
      .round-ball {
        cursor: pointer;
        width: 48px;
        height: 48px;
        display: flex;
        align-items: center;
        justify-content: center;
        border: 2px solid #000;
        font-weight: 700;
        border-radius: 100%;
        color: #000;
        &.green {
          background: #3ec70b;
        }
        &.yellow {
          background: #f7ec09;
        }
        &.red {
          background: #ff0000;
        }
      }
    }
    </style>