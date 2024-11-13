<script setup>
import { ref } from '@vue/reactivity'
import Card from 'primevue/card';
import Panel from 'primevue/panel';
import Timeline from 'primevue/timeline';
import Divider from 'primevue/divider';
import UserIcon from '../../assets/icons/UserIcon.vue'

const duties = ref([
  { name: 'Alisher Uzoqov', code: 'AU' },
  { name: 'Adiz Radjapov', code: 'BR' },
  { name: 'Kamron Boltayev', code: 'CN' },
  { name: 'Munisa Rizoyeva', code: 'EG' }
]);

</script>

<template>
  <div class="w-full space-y-4">
    <Card>
      <template #title>
        <h3 class="text-xl font-medium dark:text-white text-center mb-2">Markaz hayoti</h3>
      </template>
      <template #content>
        <p class="m-0">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore sed consequuntur error repudiandae numquam
          deserunt quisquam repellat libero asperiores earum nam nobis, culpa ratione quam perferendis esse, cupiditate
          neque quas!
        </p>
      </template>
    </Card>
    <Panel>
      <div class="flex">
        <div class="w-1/2 flex">
          <div class="w-1/2">
            <div class="w-20 h-20 bg-sky-500 rounded-full"></div>
          </div>
          <div class="w-1/2 bg-sky-500 rounded-xl h-12">
  
          </div>
        </div>
        <div class="w-1/2">
          <Timeline :value="duties">
            <template #marker="slotProps">
              <span class="flex w-8 h-8 items-center justify-center text-white rounded-full z-10 shadow-sm bg-sky-300">
                <UserIcon class="w-6 h-6 text-white" />
              </span>
            </template>
            <template #content="slotProps">
              {{ slotProps.item.name }}
            </template>
          </Timeline>
        </div>
      </div>
    </Panel>
    <Card>
      <template #title>
        <h3 class="text-xl font-medium dark:text-white text-center mb-2">Markaz hayoti</h3>
      </template>
      <template #content>
        <p class="m-0">
          Savol ???
          <Divider />
        <div class="card flex flex-wrap justify-center gap-4">
          <div class="flex items-center space-x-2">
            <input id="answer1" name="question" type="radio" class="w-4 h-4">
            <label for="answer1"> A javob </label>
          </div>
          <div class="flex items-center space-x-2">
            <input id="answer2" name="question" type="radio" class="w-4 h-4">
            <label for="answer2"> B javob </label>
          </div>
          <div class="flex items-center space-x-2">
            <input id="answer3" name="question" type="radio" class="w-4 h-4">
            <label for="answer3"> C javob </label>
          </div>
          <div class="flex items-center space-x-2">
            <input id="answer4" name="question" type="radio" class="w-4 h-4">
            <label for="answer4"> D javob </label>
          </div>
        </div>
        </p>
      </template>
    </Card>
  </div>
</template>

<style scoped></style>
