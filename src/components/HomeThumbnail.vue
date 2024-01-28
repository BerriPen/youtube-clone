<template>
  <div class="q-pa-md">
    <q-img :src="videoData.url" :ratio="16/9"/>
      <q-icon class="row">
        {{ videoData.icon}}
      </q-icon>
      <div>
        {{ videoData.title }}
          <div>
            {{ videoData.channel}}
          </div>
             <div>
                {{ videoData.views }}
              </div>
            </div>
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
