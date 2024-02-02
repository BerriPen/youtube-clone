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

      <!-- <div class="text-center">
        <v-pagination v-model="page" :length="15" :total-visible="7">
          <span v-for="(tag, index) in tags" :key="index">
              <q-btn unelevated size="sm" rounded class="q-pa-sm" color="grey-3" text-color="black" >
                <div class="q-px-xs">{{ tag }}</div>
              </q-btn>
              &nbsp;
            </span>
        </v-pagination>
      </div> -->

      <!-- Top Tag -->
      <div class="col" style="background-color: #ffffff no-wrap;">
        <div style="background-color:#ffffff;">
          <div class="row no-wrap q-mx-lg q-pb-sm">
            <span v-for="(tag, index) in tags" :key="index">
              <q-btn unelevated size="sm" rounded class="q-pa-sm" color="grey-3" text-color="black" >
                <div class="q-px-xs">{{ tag }}</div>
              </q-btn>
              &nbsp;
            </span>
          </div>
        </div>

        <!-- VIDEO -->
        <div class="q-pa-md row">
          <div class="col-6 col-md-4" v-for="(video, index) in videos" :key="index">
            <HomeThumbnail :videoInfo="video" @click="$router.push({path: '/watch', params: {text: 'hello'}})"/>
          </div>
        </div>
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
            'All','Film criticism','Speed painting','Music','Live','Mixes','Gaming', 'Podcasts', 'Movie trailer', 'Comedy', 'Watched', 'Recently uploaded', 'Anime', 'New to you'
          ],
      videos: [
        {
          title: 'THE RESIDENT EVIL MOVIES - Theyre So Bad I Cant Help But Love Them',
          channel: 'Elvis The Alien',
          icon: 'person',
          views: '8.4M views  2 years ago',
          url: 'https://i.ytimg.com/vi/Sk5cUoSRaPE/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAIgGcvSHDxlxm40JBJdlZC8D4jag'
        },
        {
          title: 'Andrew Garfield - Therapy (with Vanessa Hudgens) (Official Audio)',
          channel: 'Andrew Garfield ♪',
          icon: 'person',
          views: '557K views . 2 years ago',
          url: 'https://i.ytimg.com/vi/GBiVXdxRoQY/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLDBV6s-3-9n1TSGSgrvRuptT_mApw'
        },
        {
          title: 'Disturbing Posts I Found on Social Media',
          channel: 'LazyMasquerade',
          icon: 'person',
          views: '705K views . 7 months ago',
          url: 'https://i.ytimg.com/vi/sYXZmxNyHIk/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAGGHlvUgBYqUgAdx-b2yQmIcaTNw'
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
