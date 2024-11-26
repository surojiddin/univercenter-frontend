<script setup>
import { ref } from '@vue/reactivity'
import Card from 'primevue/card'
import Image from 'primevue/image'
import Panel from 'primevue/panel'
import Timeline from 'primevue/timeline'
import Divider from 'primevue/divider'
import UserIcon from '../../assets/icons/UserIcon.vue'

const duties = ref([
  { name: 'Alisher Uzoqov', code: 'AU' },
  { name: 'Adiz Radjapov', code: 'BR' },
  { name: 'Kamron Boltayev', code: 'CN' },
  { name: 'Munisa Rizoyeva', code: 'EG' },
])

const news = ref([
  {
    itemVideoSrc: '/videos/flower.webm',
    text: 'lorem ipsum Ayiq palvon',
  },
  {
    itemVideoSrc: '/videos/hr-recruiter.mov',
    text: 'HR recruiter bilan suhbat. Buni ko`rib mazza qilasiz.',
  },
  {
    itemVideoSrc: '/videos/movie.mp4',
    text: 'Shunchaki video.',
  },
  {
    itemVideoSrc: '/videos/movie.mp4',
    text: 'Shunchaki video. Lorem ipsum daler sit amet.',
  },
  {
    itemVideoSrc: '/videos/hr-recruiter.mov',
    text: 'HR recruiter bilan suhbat. Buni ko`rib mazza qilasiz.',
  },
])

const text = ref('Lorem ipsim doler sit amet')
const videoUrl = ref('/videos/movie.mp4')

const content = (val) => {
  text.value = news.value[val].text
  videoUrl.value = news.value[val].itemVideoSrc

  console.log(news.value[val].itemVideoSrc)
  // console.log(news[val].text)
}
</script>

<template>
  <div class="w-full space-y-4">
    <Card>
      <template #title>
        <h3 class="text-xl font-medium dark:text-white text-center mb-2">Tezkor xabarlar</h3>
      </template>
      <template #content>
        <p class="m-0">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore sed consequuntur error repudiandae numquam deserunt quisquam repellat libero asperiores earum nam nobis, culpa ratione quam perferendis esse, cupiditate neque quas!</p>
      </template>
    </Card>
    <Panel>
        <h3 class="text-xl font-medium dark:text-white text-center mb-2">Tabriklaymiz qutlaymiz !!!</h3>
      <div class="flex">
        <div class="w-1/2 flex items-center">
          <div class="w-1/2">
          <Avatar image="https://primefaces.org/cdn/primevue/images/avatar/amyelsner.png" class="mr-2" size="xlarge" shape="circle" />
            <div class="w-40 h-40 rounded-full bg-[url('/images/user-1.jpg')] bg-cover">
              <!-- <Image src="/images/user-0.jpg" class="w-full rounded-full" /> -->
            </div>
          </div>
          <div class="ml-10">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laboriosam blanditiis porro, ex facilis, ducimus consectetur quia, iure voluptates quasi qui quaerat illo quas maiores rerum sequi. Temporibus, doloribus explicabo? Aut?</div>
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
        <h3 class="text-xl font-medium dark:text-white text-center mb-2">Yangiliklar</h3>

        <div class="flex gap-4 items-center justify-between">
          <ul class="text-white flex flex-col gap-2">
            <li class="bg-sky-500 p-2 rounded cursor-pointer" @click="content(0)">Yangilik mavzusi</li>
            <li class="bg-sky-500 p-2 rounded cursor-pointer" @click="content(1)">Yangilik mavzusi</li>
            <li class="bg-sky-500 p-2 rounded cursor-pointer" @click="content(2)">Yangilik mavzusi</li>
            <li class="bg-sky-500 p-2 rounded cursor-pointer" @click="content(3)">Yangilik mavzusi</li>
            <li class="bg-sky-500 p-2 rounded cursor-pointer" @click="content(4)">Yangilik mavzusi</li>
          </ul>

          <div>
            <video controls autoplay loop style="height: 260px">
              <source :src="videoUrl" type="video/mp4" />
              Your browser does not support the video tag.
            </video>
          </div>

          <p class="flex-1">{{ text }}</p>
        </div>
      </template>
    </Card>
    <Card>
      <template #title>
        <h3 class="text-xl font-medium dark:text-white text-center mb-2">Bilasizmi?</h3>
      </template>
      <template #content>
        <p class="m-0">Savol ???</p>
        <Divider />
        <div class="card flex flex-wrap justify-center gap-4">
          <div class="flex items-center space-x-2">
            <input id="answer1" name="question" type="radio" class="w-4 h-4" />
            <label for="answer1"> A javob </label>
          </div>
          <div class="flex items-center space-x-2">
            <input id="answer2" name="question" type="radio" class="w-4 h-4" />
            <label for="answer2"> B javob </label>
          </div>
          <div class="flex items-center space-x-2">
            <input id="answer3" name="question" type="radio" class="w-4 h-4" />
            <label for="answer3"> C javob </label>
          </div>
          <div class="flex items-center space-x-2">
            <input id="answer4" name="question" type="radio" class="w-4 h-4" />
            <label for="answer4"> D javob </label>
          </div>
        </div>
      </template>
    </Card>
  </div>
</template>

<style scoped></style>
