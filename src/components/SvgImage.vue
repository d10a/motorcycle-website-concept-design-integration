<script setup lang="ts">
import { stringifyStyle } from '@vue/shared';

const props = defineProps({
  data: String,
  id: String,
  class: String
})
</script>

<template>
  <div class="svg-container" :id="id" :class="class">
    <object type="image/svg+xml" :data="data" width="100%" height="100%" class="svg-content">
    </object>
  </div>

</template>

<style lang="scss">
</style>
