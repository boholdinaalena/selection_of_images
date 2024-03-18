<template>
  <VApp>
    <SideBar @selectOption="onSelectOption" />
    <VMain>
      <ImageGallary :color="color"/>
    </VMain>
  </VApp>
</template>

<script setup>
import SideBar from "./components/SideBar.vue";
import ImageGallary from "./components/ImageGallary.vue";
import { ref } from "vue";

const color = ref("");

const onSelectOption = (newColor) => {
  color.value = newColor;
};
</script>
