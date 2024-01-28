<template>

  <q-drawer
      v-model="drawerState"
      bordered
      @hide="$emit('hide')"
    >
      <q-list padding>
        <!-- MAIN -->

        <q-item class="text-bold q-pl-md q-py-sm" v-for="(menu, index) in tabsInfo.main" :key="index" clickable>
          <q-icon color="blue-grey-10" size="sm" :name="menu.icon" />
          <span class="q-pl-sm">{{ menu.name }}</span>
        </q-item>

        <q-separator class="q-mx-lg q-my-sm"/>

        <!-- USER -->
        <q-item class="text-bold q-pl-lg q-py-sm" clickable>
          <span>You</span>
          <q-icon class="q-pl-xs" name="arrow_forward_ios"/>
        </q-item>

        <q-item class="text-bold q-pl-md q-py-sm" v-for="(menu, index) in tabsInfo.user" :key="index" clickable>
          <q-icon color="blue-grey-10" size="sm" :name="menu.icon" />
          <span class="q-pl-sm">{{ menu.name }}</span>
        </q-item>
        <q-separator class="q-mx-lg q-my-sm"/>

        <!-- SUBSCRIPTTION -->
        <q-item class="text-bold q-pl-lg q-py-sm" clickable>
          Subscriptions
        </q-item>
        <q-item class="text-bold q-pl-md q-py-sm" v-for="(menu, index) in tabsInfo.subscription" :key="index" clickable>
          <q-icon color="blue-grey-10" size="sm" :name="menu.icon" />
          <span class="q-pl-sm">{{ menu.name }}</span>
        </q-item>
        <q-separator class="q-mx-lg q-my-sm"/>

        <!-- EXPLORE -->
        <q-item class="text-bold q-pl-lg q-py-sm" clickable>
          Explore
        </q-item>

        <q-item class="text-bold q-pl-md q-py-sm" v-for="(menu, index) in tabsInfo.explore" :key="index" clickable>
          <q-icon color="blue-grey-10" size="sm" :name="menu.icon" />
          <span class="q-pl-sm">{{ menu.name }}</span>
        </q-item>

        <q-separator class="q-mx-lg q-my-sm"/>

        <!-- AccSetting -->
        <q-item class="text-bold q-pl-md q-py-sm" v-for="(menu, index) in tabsInfo.accSetting" :key="index" clickable>
          <q-icon color="blue-grey-10" size="sm" :name="menu.icon" />
          <span class="q-pl-sm">{{ menu.name }}</span>
        </q-item>

        <q-separator class="q-mx-lg q-my-sm"/>

        <!-- ExtraOps -->
        <div class="q-px-md text-blue-grey-10">
          <div class="row items center q-gutter-x-sm q-gutter-y-xs" >
            <a v-for="(menu, index) in tabsInfo.accSetting" :key="index"  class="YL__drawer-footer-link">
              {{ menu.name }}
            </a>
          </div>
        </div>

      </q-list>
    </q-drawer>
</template>
<script>

export default {
  components: {

  },
  data() {
    return {
      drawerState: this.value,
      tabsInfo: {
        main: [
          {
            name: 'Home',
            icon: 'home'
          },
          {
            name: 'Shorts',
            icon: 'shortcut'
          },
          {
            name: 'Subscriptions',
            icon: 'subscriptions'
          }
        ],
        user: [
          {
            name: 'Your channel',
            icon: 'person'
          },
          {
            name: 'History',
            icon: 'history'
          },
          {
            name: 'Your videos',
            icon: 'play_circle_outline'
          },
          {
            name: 'Watch later',
            icon: 'schedule'
          },
          {
            name: 'Your clips',
            icon: 'content_cut'
          }
        ],
        subscription:[
          {
            name: 'Pewdiepie',
            icon: 'account_circle'
          },
          {
            name: 'Bruh',
            icon: 'account_circle'
          },
          {
            name: 'Jay',
            icon: 'account_circle'
          }
        ],
        explore:[
          {
            name: 'Trending',
            icon: 'whatshot'
          },
          {
            name: 'Music',
            icon: 'music_note'
          },
          {
            name: 'Movies',
            icon: 'movie'
          },
          {
            name: 'Gaming',
            icon: 'sports_esports'
          },
          {
            name: 'News',
            icon: 'feed'
          },
          {
            name: 'Sports',
            icon: 'emoji_events'
          },
          {
            name: 'Fashion & Beauty',
            icon: 'dry_cleaning'
          }
        ],
        accSetting: [
          {
            name: 'Settings',
            icon: 'settings'
          },
          {
            name: 'Report history',
            icon: 'flag'
          },
          {
            name: 'Help',
            icon: 'help_outline'
          },
          {
            name: 'Send feedback',
            icon: 'feedback'
          },
        ],
        extraops: [
        { name: 'About' },
        { name: 'Press' },
        { name: 'Copyright' },
        { name: 'Contact us' },
        { name: 'Creators' },
        { name: 'Advertise' },
        { name: 'Developers' }
        ]
      }
    }
  },
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  watch: {
    value(val) {
      console.log('change val')
      this.drawerState = !this.drawerState
    }
  },
  async mounted () {
    console.log('Menu')
    console.log(this.value)
  },
  emits: ['hide']
}
</script>
<style>
</style>
