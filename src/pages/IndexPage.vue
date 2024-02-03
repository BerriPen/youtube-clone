<template>
  <q-page class="flex container" >
    <MenuTab @toggleDrawer="hideSide"/>

    <!-- Left Tab -->
    <div class="row q-pt-lg full-width">
      <q-list v-if="!isMobile">
        <q-item class="col-1 justice-left q-pt-sm" v-if="!hideSideMenu">
          <SideMenu/>
        </q-item>
      </q-list>

      <!-- Top Tag -->
      <div class="col" style="no-wrap">
            <div class="row no-wrap q-mx-lg q-pb-sm">
              <span v-for="(tag, index) in tags" :key="index">
                <q-btn unelevated size="sm" rounded class="q-pa-sm" color="grey-3" text-color="black" >
                  <div class="q-px-xs">{{ tag }}</div>
                </q-btn>
                &nbsp;
              </span>
          </div>

          <!-- <div class="col" style="white-space: nowrap;">
        <q-virtual-scroll v-for="(tag, index) in tags" :key="index" virtual-scroll-horizontal :v-slot="{ tag, index }">
          <div class="row no-wrap q-mx-lg q-pb-sm">
              <q-btn unelevated size="sm" rounded class="q-pa-sm" color="grey-3" text-color="black">
                <div class="q-px-xs">{{ tag }}</div>
              </q-btn>
              &nbsp;
            </div>
        </q-virtual-scroll> -->


        <!-- VIDEO -->
        <q-scroll-area style="height: 90%;">
          <div class="q-pa-md row">
            <div class="col-12 col-md-4" v-for="(video, index) in videos" :key="index">
              <HomeThumbnail :videoInfo="video" @click="$router.push({path: '/watch/'+index})"/>
            </div>
          </div>
        </q-scroll-area>
      </div>
    </div>

  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import HomeThumbnail from 'src/components/HomeThumbnail.vue'
import HomePageMenu from 'src/components/HomePageMenu.vue'
import MenuTab from 'src/components/MenuTab.vue'
import SideMenu from 'src/components/SideMenu.vue'

export default {
  name: 'IndexPage',
  components: {
    // HomePageMenu,
    HomeThumbnail,
    MenuTab,
    SideMenu
  },
  async mounted(){

  },
  data() {
    return {
      darkMode: false,
      leftDrawerOpen: false,
      hideSideMenu: false,
      isMobile: this.$q.platform.is.mobile,
      tabsInfo: {
        main: [
          {
            name: 'Home',
            icon: 'home'
          },
          {
            name: 'Stories',
            icon: 'shortcut'
          },
          {
            name: 'Subscription',
            icon: 'subscriptions'
          },
          {
            name: 'You',
            icon: 'play_circle_outline'
          }
        ]
      },
      tags:[
            'All','Film criticism','Speed painting','Music','Live','Mixes','Gaming', 'Podcasts', 'Movie trailer', 'Comedy', 'Watched', 'Zombies', 'Recently uploaded', 'Anime', 'New to you'
          ],
      videos: [
        {
          title: 'THE RESIDENT EVIL MOVIES - Theyre So Bad I Cant Help But Love Them',
          channel: 'Elvis The Alien',
          icon: 'person',
          views: '8.4M views  2 years ago',
          thumbnail: 'https://i.ytimg.com/vi/Sk5cUoSRaPE/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAIgGcvSHDxlxm40JBJdlZC8D4jag',
          url: 'https://www.youtube.com/embed/Sk5cUoSRaPE?si=lLSifSgCY2F0O1Js'
        },
        {
          title: 'when they introduce a new celebrity',
          channel: 'Daniel Thrasher',
          icon: 'person',
          views: '527K views . 1 month ago',
          thumbnail: 'https://i.ytimg.com/vi/GBiVXdxRoQY/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLDBV6s-3-9n1TSGSgrvRuptT_mApw',
          url: 'https://www.youtube.com/embed/GBiVXdxRoQY?si=VizweQTljjOId-_E'
        },
        {
          title: 'Disturbing Posts I Found on Social Media',
          channel: 'LazyMasquerade',
          icon: 'person',
          views: '705K views . 7 months ago',
          thumbnail: 'https://i.ytimg.com/vi/sYXZmxNyHIk/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAGGHlvUgBYqUgAdx-b2yQmIcaTNw',
          url: 'https://www.youtube.com/embed/sYXZmxNyHIk?si=QIGR0U_SX-w9Vim1'
        },
        {
          title: 'Carnaval Del Barrio - In The Heights Motion Picture Soundtrack (Official Audio)',
          channel: 'Atlantic Records',
          icon: 'person',
          views: '3.1M views . 2 years ago',
          thumbnail: 'https://i.ytimg.com/vi/Tmb6taDh1sQ/hqdefault.jpg?sqp=-oaymwE8CKgBEF5IWvKriqkDLwgBFQAAAAAYASUAAMhCPQCAokN4AfABAfgB1AaAAuADigIMCAAQARhyIE4oNDAP&rs=AOn4CLD98sEuGDwucOWYCMuCBIgHJt1r8A',
          url: 'https://www.youtube.com/embed/J7hAaak0QBs?si=XqZv_0rdrLBCU67C'
        },
        {
          title: 'final fantasy ⁷ ~ lofi hip hop mix',
          channel: 'Cozy',
          icon: 'person',
          views: '993K views . 4 years ago',
          thumbnail: 'https://i.ytimg.com/vi/EQwOKQKv4Pg/hq720.jpg?sqp=-oaymwE9COgCEMoBSFryq4qpAy8IARUAAAAAGAElAADIQj0AgKJDeAHwAQH4AdQGgALgA4oCDAgAEAEYZSBVKD8wDw==&rs=AOn4CLBL6AEh4wKiAjC4EAm5d1SaaG9XmQ'
        },
        {
          title: 'Memory - Elaine Paige | Cats The Musical',
          channel: 'The Shows Must Go On!',
          icon: 'person',
          views: '7.5M views . 3 years ago ',
          thumbnail: 'https://i.ytimg.com/vi/mdBVJbzkoqo/hq720.jpg?sqp=-oaymwEjCOgCEMoBSFryq4qpAxUIARUAAAAAGAElAADIQj0AgKJDeAE=&rs=AOn4CLAyHnjAknhvomUMHi_AGUkZ6qfwBA',
          url: 'https://www.youtube.com/embed/mdBVJbzkoqo?si=xZKdCW24G3NpNxS6'
        },
        {
        title: 'When He Sees Me',
        channel: 'Kimiko Glenn',
        views: '10M views . 6 years ago',
        thumbnail: 'https://i.ytimg.com/vi/JeQZY9_451w/hqdefault.jpg?sqp=-oaymwEiCKgBEF5IWvKriqkDFQgBFQAAAAAYASUAAMhCPQCAokN4AQ==&rs=AOn4CLAwK0PshcVJmWKoTA0H4sNaPh3ZNQ',
        url: 'https://www.youtube.com/embed/J7hAaak0QBs?si=XqZv_0rdrLBCU67C',

        },
        {
        title: '3 Scary TRUE Valentines Day Horror Stories',
        channel: 'Mr. Nightmare',
        views: '73,076 views . 4 hours ago',
        thumbnail: 'https://i.ytimg.com/vi/MzC9uqtHfxU/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLDJ62xL0SBaBrc1swG7T4J5s87YqA',
        url: 'https://www.youtube.com/embed/MzC9uqtHfxU?si=WLTfAAovLnFjs__N',
        }
      ]
    }
  },
  methods: {
    hideSide(val) {
      console.log('menutab: ', val)
      this.hideSideMenu = val
    }

  }
}
</script>
<style lang="scss">
.container {
  background-color: #ffff;
}
</style>
