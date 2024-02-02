<template>
  <div class="q-pa-md">
    <q-img :src="videoData.url" :ratio="16/9"/>
    <q-card class="my-card" flat>
      <q-item>
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
      videoData: this.sideVideo
    }
  },
  props: {
    sideVideo: Object
  },
  async mounted() {
    console.log('sidevideoInfo', this.sideVideo)
  }
}
</script>

<style lang="scss">

</style>
