<template>
  <VCard class="mx-5 my-4 pa-3">
    <VRow>
      <VCol v-for="n in 200" :key="n" cols="4" sm="3" md="2" lg="1">
        <VHover
>
          <VCard v-if="isVisiable" @clicl="deleteCard()">
            <VImg
              class="gallary-img"
              :src="`https://source.unsplash.com/random/600x600?&${n}&${props.color}`"
              :lazy-src="`https://source.unsplash.com/random/30x30?&${n}&${props.color}`"
              aspect-ratio="1"
              cover
            >
              <template v-slot:placeholder>
                <VRow class="fill-height ma-0" align="center" justify="center">
                  <VProgressCircular
                    indeterminate
                    color="grey-lighten-5"
                  ></VProgressCircular>
                </VRow>
              </template>
            </VImg>
          </VCard>
        </VHover>
      </VCol>
    </VRow>
  </VCard>
</template>

<script setup>
import { ref, defineProps } from "vue";

const props = defineProps(["color"]);

const isVisiable = ref(true);

const deleteCard = () => {
  isVisiable.value = false;
};
</script>
