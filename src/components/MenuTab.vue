<template>
  <q-header class="full-width">
    <q-toolbar class="q-mt-sm">
        <q-btn color="blue-grey-10"
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <div class="q-pl-sm q-mt-sm">
          <img
            src="~assets/ytlogo.png"
            style="max-width: 45 px; max-height: 23px">
        </div>

        <q-space/>

        <q-input rounded outlined v-model="text" color="blue-grey-10" dense placeholder="Search" style="width: 50%; text-align: right;">
          <template v-slot:append>
            <q-btn color="blue-grey-10" flat round dense icon="search"/>
          </template>
        </q-input>

        <q-btn color="blue-grey-10" flat round dense icon="mic"/>
        <q-space/>
        <q-btn color="blue-grey-10" flat round dense icon="file_upload"/>
        <q-btn color="blue-grey-10" flat round dense icon="notifications"/>
        <q-btn color="blue-grey-10" flat round dense icon="account_circle"/>
    </q-toolbar>
  </q-header>

  <!-- <q-footer flat elevated >
    <q-toolbar v-if="!isMobile">
      <q-list>
        <q-item class="row q-pt-sm" v-if="!hideSideMenu">
          <SideMenu/>
        </q-item>
      </q-list>
    </q-toolbar>
  </q-footer> -->

  <!-- Drawer -->
  <HomePageMenu @hide="$emit('toggleDrawer', false)" :value="leftDrawerOpen"/>
</template>
<script>
import HomePageMenu from './HomePageMenu.vue'
import SideMenu from './SideMenu.vue'

export default {
  components: {
    HomePageMenu,
    // SideMenu
  },
  data () {
    return {
      leftDrawerOpen: false,
      isMobile: this.$q.platform.is.mobile
    }
  },
  watch: {
    leftDrawerOpen (val) {
      this.$emit('toggleDrawer', true)
    }
  },
  emits:['toggleDrawer'],
  methods: {
    toggleLeftDrawer () {
      this.leftDrawerOpen = !this.leftDrawerOpen
    }
  }
}
</script>
