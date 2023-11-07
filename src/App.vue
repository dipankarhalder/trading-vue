<script setup>
import SideBar from './components/SideBar.vue'
import DashBoard from './components/DashBoard.vue'
</script>

<template>
  <div class="app_main_wrapper">
    <SideBar />
    <DashBoard />
  </div>
</template>

<style scoped>
.app_main_wrapper {
  display: flex;
}
</style>
