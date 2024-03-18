<template>
  <VNavigationDrawer expand-on-hover rail>
    <VList>
      <VListItem
        prepend-avatar="https://randomuser.me/api/portraits/women/10.jpg"
        subtitle="sandra@gmailcom"
        title="Sandra Adams"
      ></VListItem>
    </VList>

    <VDivider />

    <VList density="compact" nav>
      <VListItem
        prepend-icon="mdi-image"
        title="Color Gallary"
        value="color"
        @click="selectOption('')"
      />
      <VListItem
        prepend-icon="mdi-dialpad"
        title="Grey Gallary"
        value="greey"
        @click="selectOption('grayscale')"
      />
      <VListItem
        prepend-icon="mdi-cloud"
        title="Blue Gallary"
        value="blue"
        @click="selectOption('blue')"
      />

      <VListItem
        prepend-icon="mdi-heart"
        title="Red Gallary"
        value="red"
        @click="selectOption('red')"
      />

      <VListItem
        prepend-icon="mdi-grass"
        title="Green Gallary"
        value="green"
        @click="selectOption('green')"
      />
    </VList>
  </VNavigationDrawer>
</template>

<script setup>
import { defineEmits } from "vue";

const emits = defineEmits(["selectOption"]);

const selectOption = (color) => {
    emits('selectOption', color)
}
</script>
