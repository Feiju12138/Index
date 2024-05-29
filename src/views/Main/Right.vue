<template>
  <div :class="store.mobileOpenState ? 'right' : 'right'">
    <!-- 网站链接 -->
    <Link />
  </div>
</template>

<script setup>
import { mainStore } from "@/store";
import Link from "@/components/Links.vue";
const store = mainStore();
</script>

<style lang="scss" scoped>
.right {
  // flex: 1 0 0%;
  width: 100%;
  margin-left: 0.75rem;
}
</style>
