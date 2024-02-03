<template>
  <q-layout view="hHh Lpr lff">
    <q-page-container>
      <router-view :key="$route.fullPath"/>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'
import HomePageMenu from 'src/components/HomePageMenu.vue'

const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
]

export default defineComponent({
  name: 'MainLayout',

  data  () {
    return {
      leftDrawerOpen: false
    }
  },
  provide() {
    return {
      drawerState() {
        return this.leftDrawerOpen
      }
    }
  },
  components: {
    // EssentialLink,
    // HomePageMenu
  },
  methods: {
    toggleLeftDrawer () {
      console.log('toggle')
      this.leftDrawerOpen = !this.leftDrawerOpen
    }
  },
  setup () {
    // const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList
    }
  }
})
</script>
