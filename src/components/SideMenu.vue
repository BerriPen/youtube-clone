<template>
<q-list>
  <div class="text-center q-py-sm" v-for="(menu, index) in main" :key="index" clickable>
    <q-icon color="blue-grey-10" size="sm" :name="menu.icon" />
    <div class="q-pt-sm" style="font-size: 11px;">{{ menu.name }}</div>
  </div>
</q-list>
</template>
<script>
export default {
  data() {
    return {
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
    }
  }
}
</script>
