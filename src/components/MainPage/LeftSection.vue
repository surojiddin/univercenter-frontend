<script setup>
import { ref } from '@vue/reactivity'
import Image from 'primevue/image';
import Carousel from 'primevue/carousel';
import PanelMenu from 'primevue/panelmenu';
import Listbox from 'primevue/listbox';
import UserIcon from '../../assets/icons/UserIcon.vue'

const products = ref([
  {
    title: "14-yanvar Vatan ximoyachilar kuni",
    image: "https://primefaces.org/cdn/primevue/images/galleria/galleria10.jpg"
  },
  {
    title: "8-dekabr Vatan ximoyachilar kuni",
    image: "https://primefaces.org/cdn/primevue/images/galleria/galleria10.jpg"
  }
]);

const items = ref([
  {
    label: "1-o'quv kanfedra",
    icon: 'pi pi-palette',
    items: [
      {
        label: 'Styled',
        icon: 'pi pi-eraser',
        route: '/theming/styled'
      },
      {
        label: 'Unstyled',
        icon: 'pi pi-heart',
        route: '/theming/unstyled'
      }
    ]
  },
  {
    label: "2-o'quv kanfedra",
    icon: 'pi pi-link',
    command: () => {
      router.push('/introduction');
    }
  },
  {
    label: "3-o'quv kanfedra",
    icon: 'pi pi-home',
    items: [
      {
        label: 'Vue.js',
        icon: 'pi pi-star',
        url: 'https://vuejs.org/'
      },
      {
        label: 'Vite.js',
        icon: 'pi pi-bookmark',
        url: 'https://vuejs.org/'
      }
    ]
  }
]);

const duties = ref([
  { name: 'Alisher Uzoqov', code: 'AU' },
  { name: 'Adiz Radjapov', code: 'BR' },
  { name: 'Kamron Boltayev', code: 'CN' },
  { name: 'Munisa Rizoyeva', code: 'EG' }
]);

</script>

<template>
  <div class="w-full space-y-4">
    <h3 class="text-xl font-medium dark:text-white text-center mb-2">Tadbirlar</h3>
    <div>
      <Carousel :value="products" :numVisible="1" :numScroll="1" circular :autoplayInterval="3000">
        <template #item="slotProps">
          <div class="border border-surface-200 dark:border-surface-700 rounded m-1 p-2">
            <div class="mb-2">
              <div class="relative mx-auto">
                <Image src="https://primefaces.org/cdn/primevue/images/galleria/galleria10.jpg" alt="#" width="250"
                  class="w-full rounded" />
              </div>
            </div>
            <div class="font-medium">{{ slotProps.data.title }}</div>
          </div>
        </template>
      </Carousel>
    </div>

    <div>
      <PanelMenu :model="items" class="w-full">
        <template #item="{ item }">
          <router-link v-if="item.route" v-slot="{ href, navigate }" :to="item.route" custom>
            <a v-ripple class="flex items-center cursor-pointer dark:text-surface-0 px-4 py-2" :href="href"
              @click="navigate">
              <span :class="item.icon" />
              <span class="ml-2">{{ item.label }}</span>
            </a>
          </router-link>
          <a v-else v-ripple class="flex items-center cursor-pointer dark:text-surface-0 px-4 py-2" :href="item.url"
            :target="item.target">
            <span :class="item.icon" />
            <span class="ml-2">{{ item.label }}</span>
            <span v-if="item.items" class="pi pi-angle-down text-primary ml-auto" />
          </a>
        </template>
      </PanelMenu>
    </div>

    <Listbox :options="duties" optionLabel="name" class="w-full" listStyle="max-height:100px">
      <template #option="slotProps">
        <div class="flex items-center space-x-2">
          <UserIcon class="w-6 h-6 text-white" />
          <div>{{ slotProps.option.name }}</div>
        </div>
      </template>
    </Listbox>
  </div>
</template>

<style scoped></style>
