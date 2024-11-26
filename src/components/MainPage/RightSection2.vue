<script setup>
import { ref } from '@vue/reactivity'
import Galleria from 'primevue/galleria'
// import Video from 'primevue/video'
import Panel from 'primevue/panel'
import Button from 'primevue/button'

const images = ref([
  {
    itemVideoSrc: '/videos/mov_bbb.mp4',
    thumbnailImageSrc: 'https://primefaces.org/cdn/primevue/images/galleria/galleria1s.jpg',
  },
  {
    itemVideoSrc: '/videos/hr-recruiter.mov',
    thumbnailImageSrc: 'https://primefaces.org/cdn/primevue/images/galleria/galleria2s.jpg',
  },
  {
    itemVideoSrc: '/videos/movie.mp4',
    thumbnailImageSrc: 'https://primefaces.org/cdn/primevue/images/galleria/galleria3s.jpg',
  },
  {
    itemVideoSrc: '/videos/movie.mp4',
    thumbnailImageSrc: 'https://primefaces.org/cdn/primevue/images/galleria/galleria4s.jpg',
  },
  {
    itemVideoSrc: '/videos/hr-recruiter.mov',
    thumbnailImageSrc: 'https://primefaces.org/cdn/primevue/images/galleria/galleria5s.jpg',
  },
])

const responsiveOptions = ref([
  {
    breakpoint: '1300px',
    numVisible: 4,
  },
  {
    breakpoint: '575px',
    numVisible: 1,
  },
])
</script>

<template>
  <div class="w-full space-y-2">
    <h3 class="text-xl font-medium dark:text-white text-center mb-2">Markaz hayoti</h3>
    <Galleria :value="images" :responsiveOptions="responsiveOptions" :numVisible="5" containerStyle="max-width: 640px">
      <template #item="slotProps">
        <video controls ref="videoPlayer" style="height: 200px; width: 100%;" autoplay loop>
          <source :src="slotProps.item.itemVideoSrc" type="video/mp4" />
          Your browser does not support the video tag.
        </video>

        <!-- <video width="100%" ref="videoPlayer" controls @ended="onVideoEnd">
          <source :src="slotProps.item.itemVideoSrc" type="video/mp4" />
          Your browser does not support the video tag.
        </video> -->
        <!-- <Video :src="slotProps.item.itemVideoSrc"></Video> -->
        <!-- <img :src="slotProps.item.itemImageSrc" alt="#" style="width: 100%" /> -->
      </template>
      <template #thumbnail="slotProps">
        <img :src="slotProps.item.thumbnailImageSrc" alt="#" />
      </template>
    </Galleria>
    <Panel>
      <div class="space-y-1 mb-2">
        <h3 class="text-lg font-medium dark:text-white text-center mb-2">1-kurs</h3>
        <div class="flex space-x-1">
          <Button label="Dars jadvali" severity="info" size="small" class="w-1/2" />
          <Button label="Nazoratlar" severity="info" size="small" class="w-1/2" />
        </div>
        <Button label="Yetakchi tinglovchilar" severity="info" size="small" class="w-full" />
      </div>
      <div class="space-y-1 mb-2">
        <h3 class="text-lg font-medium dark:text-white text-center mb-2">2-kurs</h3>
        <div class="flex space-x-1">
          <Button label="Dars jadvali" severity="info" size="small" class="w-1/2" />
          <Button label="Nazoratlar" severity="info" size="small" class="w-1/2" />
        </div>
        <Button label="Yetakchi tinglovchilar" severity="info" size="small" class="w-full" />
      </div>
      <div class="space-y-1">
        <h3 class="text-lg font-medium dark:text-white text-center mb-2">MOK</h3>
        <div class="flex space-x-1">
          <Button label="Dars jadvali" severity="info" size="small" class="w-1/2" />
          <Button label="Nazoratlar" severity="info" size="small" class="w-1/2" />
        </div>
      </div>
    </Panel>
  </div>
</template>

<style scoped></style>
