<script setup lang="ts"></script>
<template>
  <a-layout>
    <a-layout-header class="header"></a-layout-header>
    <a-layout-content class="content">Content</a-layout-content>
    <a-layout-footer class="footer">Footer</a-layout-footer>
  </a-layout>
</template>

<style scoped>
.header {
  height: 40px;
  width: 100%;
  position: sticky;
  top: 0;
  left: 0;
}
</style>
