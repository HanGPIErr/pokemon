<template>

        <nav class="header-container">
    <svg
      width="136"
      height="48"
      viewBox="0 0 136 48"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <circle cx="24" cy="24" r="24" fill="#00D7FF" />
      <circle cx="18" cy="18" r="12" fill="url(#paint0_radial_367_80)" />
      <circle cx="72" cy="8" r="7.5" fill="#FF0000" stroke="#2C3333" />
      <circle cx="100" cy="8" r="7.5" fill="#F7EC09" stroke="#2C3333" />
      <circle cx="128" cy="8" r="7.5" fill="#3EC70B" stroke="#2C3333" />
      <defs>
        <radialGradient
          id="paint0_radial_367_80"
          cx="0"
          cy="0"
          r="1"
          gradientUnits="userSpaceOnUse"
          gradientTransform="translate(18 18) rotate(77.0054) scale(12.3154)"
        >
          <stop stop-color="white" />
          <stop offset="1" stop-color="white" stop-opacity="0" />
        </radialGradient>
      </defs>
    </svg>
    <img src="../assets/header_line.png" class="header-line" />
  </nav>
  
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue'
  
  export default defineComponent({
    setup() {
  
      return {}
    }
  
  })
  </script>
  
<style lang="scss" scoped>
.header-container {
  height: 80px;
  padding-top: 10px;
  padding-left: 12px;
  .header-line {
    position: absolute;
    top: 20px;
    left: 0;
    right: 0;
    width: 100%;
    height: 48px;
  }
}
</style>