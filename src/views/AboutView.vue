<template>
  <div class="bg-red-200 h-screen w-full flex justify-center items-center">
    <!-- <h1>This is an about page</h1> -->
    <OptComponent :digit-count="6" />
  </div>
</template>

<script setup lang="ts">
import OptComponent from '@/components/opt/optComponent.vue';

</script>