<template>
  <div class="q-pa-md">
    <q-img :src="videoData.url" :ratio="16/9"/>
      <q-card class="my-card" flat>
        <q-item>
          <q-item-section avatar>
            <q-avatar size="lg">
              <img src="https://cdn.quasar.dev/img/boy-avatar.png">
            </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ videoData.title }}</q-item-label>
                <q-item-label caption>
                  {{ videoData.channel }}
                </q-item-label>
                <q-item-label caption>
                  {{ videoData.views }}
                </q-item-label>
             </q-item-section>
        </q-item>
      </q-card>
  </div>
</template>



<script>
export default {
  data() {
    return{
      videoData: this.videoInfo
    }
  },
  props: {
    videoInfo: Object
  },
  async mounted() {
    console.log('videoInfo', this.videoInfo)
  }
}
</script>

<style lang="scss">

</style>
