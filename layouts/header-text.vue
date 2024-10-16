<script setup lang="ts">
import { computed } from "vue";

const props = defineProps({
  headerClass: {
    type: String,
  },
  class: {
    type: String,
  },
});
</script>

<!-- header-text.vue -->
<template>
  <div class="slidev-layout header-text">
    <div class="header" :class="headerClass">
      <slot name="header" />
    </div>
    <div class="text" :class="class">
      <slot name="text" />
    </div>
  </div>
</template>

<style scoped>
.slidev-layout.header-text {
  display: flex;
  flex-direction: column;
}

.text {
  flex: 1;
  display: flex;
  align-items: center; /* This centers the content vertically */
}
</style>
