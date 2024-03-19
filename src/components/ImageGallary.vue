<template>
  <VCard class="mx-5 my-4 pa-3">
    <VRow>
      <VCol v-for="n in arrKey" :key="n" cols="6" sm="4" md="3" lg="2">
        <VHover
>
          <VCard class="container" v-if="isVisiable" @click="reloadCard(n)">
            <VImg
              class="gallary-img"
              :src="`https://source.unsplash.com/random/600x600?&${n}&${props.color}`"
              :lazy-src="`https://source.unsplash.com/random/600x600?&${n}&${props.color}`"
              aspect-ratio="1"
              cover
            >
            <img class="reload" src="../assets/img_72363.png" alt="">
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
import { ref, defineProps,onMounted, reactive } from "vue";

const props = defineProps(["color"]);

const isVisiable = ref(true);

const gallaryLength = 100;
let counter = 100


const arrKey = reactive(Array.from({length: gallaryLength}, (_, i) =>  i + 1));

const reloadCard = (i) => {
  const index = arrKey.indexOf(i)
  arrKey.splice(index, 1, i+counter);
}
</script>

<style lang="scss" scoped>
.reload {
  width: 100%;
  padding: 35%;
  display: block;
  justify-content: right;
  background-color: rgba(255, 255, 255, 0.413);
  visibility: hidden;
}

.container:hover{
  .reload {
  visibility: visible;
}
}
.container::after{
  .reload {
  visibility: hidden;
}
}
</style>