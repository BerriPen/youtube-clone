<template>
  <q-page class="q-ml-md q-mt-md">
    <MenuTab @toggleDrawer="hideSide"/>
    <div class="q-pa-md column-wrapping">
      <div class="row">
        <div class="col-8">
          <div class="q-pa-md">
            <q-card class="videos" flat style="height: fit-content;">
              <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ?rel=0" :ratio="16/9"/>
                <q-card-section>
                  <div class="text-h6">Our Changing Planet</div>
                  <div class="text-subtitle2">by John Doe</div>
                </q-card-section>

                <q-card-section class="q-pt-none">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                  eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </q-card-section>
              </q-card>
            </div>
          </div>
          <div class="col-4">
            <div class="q-mz-sm q-mt-md">
              <q-card flat>
                <q-card-section horizontal>
                  <div v-for="(sideVideo, index) in sideVideos" :key="index">
                    <q-card style="width: 160px; height: 100px;" flat>
                      <q-img :src="sideVideo.url" alt="Side Video"></q-img>
                      <q-card-section horizontal>
                        <div>{{ sideVideo.title}}</div>
                        <div>{{ sideVideo.channel }}</div>
                      </q-card-section>
                    </q-card>
                  </div>
                </q-card-section>
              </q-card>
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import MenuTab from 'src/components/MenuTab.vue'
import HomeThumbnail from 'src/components/HomeThumbnail.vue'
export default{
  components:{
    MenuTab,

  },
  props: {
    // videoData: {
    //   title: '',
    //   url: null,
    //   views: null,
    //   thumbnail: null
    // }
  },
  data(){
    return{
      leftDrawerOpen: false,
      hideSideMenu: false,
      sideVideos:[
        {
        title: 'Carnaval Del Barrio - In The Heights Motion Picture Soundtrack (Official Audio)',
        channel: 'Atlantic Records',
        views: '3.1M views  2 years ago',
        url: 'https://i.ytimg.com/vi/Tmb6taDh1sQ/hqdefault.jpg?sqp=-oaymwE8CKgBEF5IWvKriqkDLwgBFQAAAAAYASUAAMhCPQCAokN4AfABAfgB1AaAAuADigIMCAAQARhyIE4oNDAP&rs=AOn4CLD98sEuGDwucOWYCMuCBIgHJt1r8A'
        }
      ]
    }
  },
  methods:{
    hideSide(val) {
      console.log('menutab: ', val)
      this.hideSideMenu = val
    }
  },
  async mounted () {
    console.log('params: ', this.$route.params)
  }
}


</script>
<style lang="scss" scoped>
.videos {
  width: 100%;
  height: auto;
  max-width:800px;
}
</style>

