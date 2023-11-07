<script setup>
import { sidebaritems } from './utility/content'
</script>

<template>
  <div class="app_sidebar">
    <div class="app_logo">
      <span>Trading Logo</span>
    </div>
    <div class="app_navigation">
      <ul>
        <li v-for="item in sidebaritems" :key="item.title">
          <span></span>
          <p>{{item.title}}</p>
        </li>
        <!-- <li><v-icon name="activity" class="v-icon"></v-icon></li>
        <li><v-icon name="pocket"></v-icon></li> -->
      </ul>
    </div>
  </div>
</template>

<style scoped>
.app_sidebar {
  display: flex;
  width: 260px;
  height: 100vh;
  flex-direction: column;
}
.app_logo {
  padding: 30px 40px;
  box-sizing: border-box;
}
.app_logo > span {
  float: left;
  width: 100%;
  font-size: 30px;
  font-weight: 600;
  /* color: var(--white); */
}
.app_navigation ul{
  display: flex;
  flex-direction: column;
}
.app_navigation ul li {
  margin-bottom: 16px;
  display: flex;
  align-items: center;
}
.app_navigation ul li > span {
  width: 24px;
  height: 24px;
  border-radius: 3px;
  margin-right: 10px;
  background: var(--vt-c-indigo);
}
.app_navigation ul li p{
  font-weight: 500;
}
</style>
