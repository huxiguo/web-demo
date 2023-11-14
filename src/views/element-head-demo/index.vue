<script setup lang="ts">
import ElementDemoContent from '@/components/element-demo-content/index.vue'
</script>
<template>
  <a-layout>
    <a-layout-header class="header"></a-layout-header>
    <a-layout-content class="content">
      <ElementDemoContent />
    </a-layout-content>
    <a-layout-footer class="footer">Footer</a-layout-footer>
  </a-layout>
</template>

<style scoped>
.header {
  width: 100%;
  position: sticky;
  top: 0;
  left: 0;
  background-image: radial-gradient(transparent 1px, #fff 1px);
  background-size: 4px 4px;
  backdrop-filter: saturate(50%) blur(5px);
  border-bottom: 1px solid #e8e8e8;
  z-index: 999;
  background-color: transparent;
}
.content {
  width: 100%;
  /* height: 900px; */
  padding: 18px;
}
</style>
