<template>
  <q-page class="flex container" >
    <MenuTab @toggleDrawer="hideSide"/>

    <!-- Left Tab -->
    <div class="row q-pt-lg full-width">
      <div class="col-1 justice-left q-pt-sm" v-if="!hideSideMenu">
        <SideMenu/>
        <!-- <q-list>
          <div class="text-center q-py-sm" v-for="(menu, index) in tabsInfo.main" :key="index">
            <q-icon color="blue-grey-10" size="sm" :name="menu.icon" />
            <div class="q-pt-sm" style="font-size: 11px;">{{ menu.name }}</div>
          </div>
        </q-list> -->
      </div>

      <!-- Top Tag -->
      <div class="col" style="background-color: aqua;">
        <div style="background-color:#ffffff;">
          <div class="q-mx-lg q-pb-sm">
            <span v-for="(tag, index) in tags" :key="index">
              <q-btn unelevated size="sm" rounded class="q-pa-sm" color="grey-3" text-color="black" >
                <div class="q-px-xs">{{ tag }}</div>
              </q-btn>
              &nbsp;
            </span>
          </div>
        </div>

        <!-- VIDEO -->
        <div class="row items-center">
          <div class="col" v-for="(video, index) in videos" :key="index">
            <HomeThumbnail :videoInfo="video"/>
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
          title: 'The Prince of Egypt Musical | When You Believe',
          channel: 'The Prince Of Egypt Musical',
          url: 'https://www.youtube.com/watch?v=bHi-1Ekk3KE'
        },
        {
          title: 'Andrew Garfield - Therapy (with Vanessa Hudgens) (Official Audio)',
          channel: 'Andrew Garfield ♪',
          url: 'https://i.ytimg.com/vi/sYXZmxNyHIk/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAGGHlvUgBYqUgAdx-b2yQmIcaTNw'
        },
        {
          title: 'Disturbing Posts I Found on Social Media',
          channel: 'LazyMasquerade',
          url: 'https://i.ytimg.com/vi/GBiVXdxRoQY/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLDBV6s-3-9n1TSGSgrvRuptT_mApw'
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
