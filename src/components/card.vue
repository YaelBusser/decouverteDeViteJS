<template>
  <div class="card">
    <div class="card-body">
      <!-- Notation particulière à VueJS -->
      <slot></slot>
      <button :class="color">{{ label }}</button>
    </div>
  </div>
</template>

<script setup lang="ts">
  const props = defineProps({
    label: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      required: true,
    },
  });
</script>

<style scoped>
.red{
background-color: red;
}
</style>