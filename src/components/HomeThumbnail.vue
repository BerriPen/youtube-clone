<template>
  <div>
    <q-image :src="videoData.url"/>
    {{ videoData.title }}
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
