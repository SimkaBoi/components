<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      class="grey darken-4"
    >
      <v-list nav dense>
        <v-list-item
          v-for="[icon, text] in links_main"
          :key="icon"
          link
        >
          <v-list-item-icon>
            <v-icon color="grey">{{ icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider></v-divider>
      <v-list nav dense>
        <v-list-item
          v-for="[icon, text] in links_secondary"
          :key="icon"
          link
        >
          <v-list-item-icon>
            <v-icon color="grey">{{ icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider></v-divider>
      <v-list nav dense>
        <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>
            TELLIMUSED
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
        <v-list-item
          v-for="[avatar, name] in subscriptions"
          :key="avatar"
          link
        >
          <v-list-item-avatar size="25">
          <v-img
            :alt="`${name} avatar`"
            :src="avatar"
          ></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title v-text="name"></v-list-item-title>
        </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>




    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Youtube',
      cards: ['Today', 'Yesterday'],
      links_main: [
        ['mdi-home', 'Avaleht'],
        ['mdi-fire', 'Populaarsed'],
        ['mdi-youtube-subscription', 'Tellimused'],
      ],
      links_secondary: [
        ['mdi-play-box-multiple', 'Kogu'],
        ['mdi-history', 'Ajalugu'],
        ['mdi-play-box-outline', 'Teie videod'],
        ['mdi-clock', 'Hiljem vaatamiseks'],
        ['mdi-playlist-play', 'Lemmikud'],
        ['mdi-thumb-up', 'Meeldinud videod'],
      ],
      subscriptions: [
        ['https://yt3.ggpht.com/ytc/AAUvwniGuwmwnYd63hDKeebvj4KBUBvouY3FtszqSRMrYw=s88-c-k-c0x00ffffff-no-rj', 'Sidemen'],
        ['https://yt3.ggpht.com/ytc/AAUvwninLx6_ZEJLBDLKYaB-9KMKLb5aQOoFUC_cx-Kz=s88-c-k-c0x00ffffff-no-rj', 'SidemenReacts'],
        ['https://yt3.ggpht.com/ytc/AAUvwniVxsVsLQpT-pOCm1CpW1sG5PkFRBbAe4jExlSClg=s88-c-k-c0x00ffffff-no-rj', 'MoreSidemen'],
        ['https://yt3.ggpht.com/ytc/AAUvwnjbH0uVPRm82votoF1QMjuJbudQvTJjrR_cBOYyog=s88-c-k-c0x00ffffff-no-rj', 'SwaggerSouls'],
        ['https://yt3.ggpht.com/ytc/AAUvwnipIOGF5oWVbSffcVHhvJm5guRr4A21wbbmy1NX=s88-c-k-c0x00ffffff-no-rj', 'LEMMiNO'],
        ['https://yt3.ggpht.com/ytc/AAUvwnj4Nx2WoQcBF-mPsUhE8H4Xvvasx17DwhJ14MzQ3Q=s88-c-k-c0x00ffffff-no-rj', 'Pyrocynical'],
        ['https://yt3.ggpht.com/ytc/AAUvwnhKr-KpJ_6VZDp1UHjpfnEjIQYQnxKQNMUg3WCMiw=s88-c-k-c0x00ffffff-no-rj', 'Callux'],
      ]
    }
  }
}
</script>
