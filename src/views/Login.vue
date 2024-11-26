<script setup>
import { ref, reactive } from '@vue/reactivity'
import { useRouter } from 'vue-router'
import { useAuthStore } from '../store/auth.store'
import EyeIcon from '../assets/icons/EyeIcon.vue'
import EyeSlashIcon from '../assets/icons/EyeSlashIcon.vue'
import AuthService from '../services/auth.service'
import { onMounted } from 'vue'
import notify from 'izitoast'
import 'izitoast/dist/css/iziToast.min.css'
import i18n from '../i18n.js'
import { useI18n } from 'vue-i18n'
import decodeJwt from '../mixins/utils'
import UserIcon from '../assets/icons/UserIcon.vue'
import NewsIcon from '../assets/icons/NewsIcon.vue'
import moment from 'moment'

import Checkbox from 'primevue/checkbox';

import Divider from 'primevue/divider';
import Card from 'primevue/card';
import Image from 'primevue/image';
import Carousel from 'primevue/carousel';
import PanelMenu from 'primevue/panelmenu';
import Listbox from 'primevue/listbox';

import Panel from 'primevue/panel';
import Timeline from 'primevue/timeline';

import Button from 'primevue/button';


import Fieldset from 'primevue/fieldset';

import Galleria from 'primevue/galleria';


import Splitter from 'primevue/splitter';
import SplitterPanel from 'primevue/splitterpanel';

import HeaderSection from '../components/MainPage/HeaderSection.vue'
import LeftSection from '../components/MainPage/LeftSection.vue'
import FooterSection from '../components/MainPage/FooterSection.vue'
import RightSection from '../components/MainPage/RightSection2.vue'
import MainSection from '../components/MainPage/MainSection2.vue'

const { t } = useI18n()
const isLoading = ref(false)
const hidePassword = ref(true)
const router = useRouter()

const lang = ref('')

const changeLang = () => {
  localStorage.setItem('lang', lang.value)
  i18n.global.locale.value = lang.value
  document.getElementsByTagName('title')[0].innerHTML = t('title')
}

onMounted(() => {
  lang.value = localStorage.getItem('lang') || 'uz'
  document.getElementsByTagName('title')[0].innerHTML = t('title')
})

</script>

<template>
  <div class="flex flex-col">
    <HeaderSection />
    <div class="w-full container mx-auto pt-6 pb-3">
      <div class="flex space-x-4 w-full">
        <LeftSection class="w-1/5" />
        <MainSection class="w-3/5" />
        <RightSection class="w-1/5" />
      </div>
    </div>
    <FooterSection />
  </div>
</template>

<style scoped></style>
