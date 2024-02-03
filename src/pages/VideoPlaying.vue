<template>
  <q-page class="q-ml-md q-mt-md" v-if="isLoaded">
    <MenuTab @toggleDrawer="hideSide"/>
      <div class="q-pa-md -pt-md column-wrapping">

        <!-- VIDEO AREA -->
        <div class="row">
          <div class="col-8">

            <!-- VIDEO -->
              <q-card class="videos" flat style="height: fit-content;">
                <q-video :src="video.url" :ratio="16/9" loading="lazy"/>
                <!-- DESCRIPTION -->
                <q-item-label class="text-h5 q-pt-sm">{{ video.title }}</q-item-label>
                <q-card-section>
                    <q-item>
                      <q-item-section avatar>
                        <q-avatar>
                          <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                        </q-avatar>
                      </q-item-section>
                      <!-- Titleass -->
                      <q-item-section>
                        <q-item-label>{{ video.channel }}</q-item-label>
                        <q-item-label caption>
                          1,000,000
                        </q-item-label>
                      </q-item-section>
                      <q-btn unelevated rounded color="grey-10" label="Subscribe" />

                      <q-btn unelevated rounded icon="thumb_up"/>
                      <q-btn unelevated rounded icon="thumb_down"/>
                      <q-btn unelevated rounded icon="share" label="Share"/>
                      <q-btn unelevated rounded icon="more_horiz"/>
                    </q-item>

                  <!-- <div class="text-h6">Our Changing Planet</div>
                  <div class="text-subtitle2">by John Doe</div> -->

                </q-card-section>
                <div class="text-bold">{{ video.views }}</div>
                <q-card-section class="q-pt-none">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, seddo
                    eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </q-card-section>

                <q-card-section>
                  <q-item-label class="text-h5 q-pt-sm">Comments</q-item-label>
                </q-card-section>
              </q-card>
          </div>

          <!-- SUGGESTED VIDS -->

          <div class="col-4">
            <div class="row q-mt-md">

            <!-- THUMBNAIL -->

              <div class="col-12 col-md">
                <q-list>
                  <q-card class="q-pr-md" flat>
                    <div class="row" v-for="(sideVideo, index) in sideVideos" :key="index" @click="$router.push({path: '/watch/'+index})">
                      <div class="col-12 col-md-2">
                        <q-card style="width: 160px; height: 100px;" flat>
                          <q-img :src="sideVideo.thumbnail" alt="Side Video"></q-img>
                        </q-card>
                      </div>
                      <div class="col-12 col-md-7" style="margin-left: 100px">
                        <div>{{ sideVideo.title}}</div>
                        <div>{{ sideVideo.channel }}</div>
                        <div>{{ sideVideo.views }}</div>
                      </div>
                    </div>
                  </q-card>
                </q-list>
              </div>
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
    MenuTab

  },
  props: {
    id: Number
  },
  data(){
    return{
      leftDrawerOpen: false,
      hideSideMenu: false,
      isLoaded: false,
      video: null,
      sideVideos:[
      {
          title: 'THE RESIDENT EVIL MOVIES - Theyre So Bad I Cant Help But Love Them',
          channel: 'Elvis The Alien',
          icon: 'person',
          views: '8.4M views  2 years ago',
          thumbnail: 'https://i.ytimg.com/vi/Sk5cUoSRaPE/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAIgGcvSHDxlxm40JBJdlZC8D4jag',
          url: 'https://www.youtube.com/embed/Sk5cUoSRaPE?si=lLSifSgCY2F0O1Js'
        },
        {
          title: 'when they introduce a new celebrity',
          channel: 'Daniel Thrasher',
          icon: 'person',
          views: '527K views . 1 month ago',
          thumbnail: 'https://i.ytimg.com/vi/GBiVXdxRoQY/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLDBV6s-3-9n1TSGSgrvRuptT_mApw',
          url: 'https://www.youtube.com/embed/GBiVXdxRoQY?si=VizweQTljjOId-_E'
        },
        {
          title: 'Disturbing Posts I Found on Social Media',
          channel: 'LazyMasquerade',
          icon: 'person',
          views: '705K views . 7 months ago',
          thumbnail: 'https://i.ytimg.com/vi/sYXZmxNyHIk/hq720.jpg?sqp=-oaymwEXCNAFEJQDSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLAGGHlvUgBYqUgAdx-b2yQmIcaTNw',
          url: 'https://www.youtube.com/embed/sYXZmxNyHIk?si=QIGR0U_SX-w9Vim1'
        },
        {
          title: 'Carnaval Del Barrio - In The Heights Motion Picture Soundtrack (Official Audio)',
          channel: 'Atlantic Records',
          icon: 'person',
          views: '3.1M views . 2 years ago',
          thumbnail: 'https://i.ytimg.com/vi/Tmb6taDh1sQ/hqdefault.jpg?sqp=-oaymwE8CKgBEF5IWvKriqkDLwgBFQAAAAAYASUAAMhCPQCAokN4AfABAfgB1AaAAuADigIMCAAQARhyIE4oNDAP&rs=AOn4CLD98sEuGDwucOWYCMuCBIgHJt1r8A',
          url: 'https://www.youtube.com/embed/J7hAaak0QBs?si=XqZv_0rdrLBCU67C'
        },
        {
          title: 'final fantasy ⁷ ~ lofi hip hop mix',
          channel: 'Cozy',
          icon: 'person',
          views: '993K views . 4 years ago',
          thumbnail: 'https://i.ytimg.com/vi/EQwOKQKv4Pg/hq720.jpg?sqp=-oaymwE9COgCEMoBSFryq4qpAy8IARUAAAAAGAElAADIQj0AgKJDeAHwAQH4AdQGgALgA4oCDAgAEAEYZSBVKD8wDw==&rs=AOn4CLBL6AEh4wKiAjC4EAm5d1SaaG9XmQ'
        },
        {
          title: 'Memory - Elaine Paige | Cats The Musical',
          channel: 'The Shows Must Go On!',
          icon: 'person',
          views: '7.5M views . 3 years ago ',
          thumbnail: 'https://i.ytimg.com/vi/mdBVJbzkoqo/hq720.jpg?sqp=-oaymwEjCOgCEMoBSFryq4qpAxUIARUAAAAAGAElAADIQj0AgKJDeAE=&rs=AOn4CLAyHnjAknhvomUMHi_AGUkZ6qfwBA',
          url: 'https://www.youtube.com/embed/mdBVJbzkoqo?si=xZKdCW24G3NpNxS6'
        },
        {
        title: 'When He Sees Me',
        channel: 'Kimiko Glenn',
        views: '10M views . 6 years ago',
        thumbnail: 'https://i.ytimg.com/vi/JeQZY9_451w/hqdefault.jpg?sqp=-oaymwEiCKgBEF5IWvKriqkDFQgBFQAAAAAYASUAAMhCPQCAokN4AQ==&rs=AOn4CLAwK0PshcVJmWKoTA0H4sNaPh3ZNQ'
        },
        {
        title: 'Carnaval Del Barrio - In The Heights Motion Picture Soundtrack (Official Audio)',
        channel: 'Atlantic Records',
        views: '3.1M views  2 years ago',
        thumbnail: 'https://i.ytimg.com/vi/Tmb6taDh1sQ/hqdefault.jpg?sqp=-oaymwE8CKgBEF5IWvKriqkDLwgBFQAAAAAYASUAAMhCPQCAokN4AfABAfgB1AaAAuADigIMCAAQARhyIE4oNDAP&rs=AOn4CLD98sEuGDwucOWYCMuCBIgHJt1r8A'
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
    console.log('id', this.id)
    this.video = this.sideVideos[this.id]

    this.isLoaded = true
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

