<script setup>
import moment from 'moment'
import Panel from 'primevue/panel';

</script>

<template>
  <div class="w-full container mx-auto pt-4 pb-3">
    <div class="flex items-center space-x-4 w-full">
      <div class="flex-1 bg-sky-500 rounded-xl py-3 px-4 text-xl text-center text-white">
        {{ moment().format('D-MM-YYYY H:mm') }}
      </div>
      <div class="flex items-center justify-between w-3/5 bg-sky-500 rounded-tl-[50px] rounded-br-[50px] py-2 px-10">
        <div class="w-16 h-16 bg-sky-600 rounded-full"></div>
        <div class=" text-3xl font-medium text-center text-white uppercase">
          <div>Institut markazining</div>
          <div>xabarlar oynasi</div>
        </div>
        <div class="w-16 h-16 bg-sky-600 rounded-full"></div>
      </div>
      <div class="flex-1 bg-sky-500 rounded-xl py-3 px-4 text-xl text-center text-white">
        Ob-havo
      </div>
    </div>
  </div>
  <div class="w-full text-center text-lg py-1 text-white bg-sky-500">Kun shiori</div>
</template>

<style scoped></style>
