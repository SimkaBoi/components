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
      <div v-if="miniVariant">
        <v-list nav dense>
          <v-list-item v-for="[icon, text] in links_mini" :key="icon" link>
            <div class="d-flex flex-column align-left">
              <v-list-item-icon>
                <v-icon color="grey">{{ icon }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content style="text-align=left;">
                <v-list-item-title>{{ text }}</v-list-item-title>
              </v-list-item-content>
            </div>
          </v-list-item>
        </v-list>
      </div>
      <div v-else>
        <v-list nav dense>
          <v-list-item v-for="[icon, text] in links_main" :key="icon" link>
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
          <v-list-item v-for="[icon, text] in links_secondary" :key="icon" link>
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
            v-for="[avatar, name, notification] in subscriptions"
            :key="avatar"
            link
          >
            <v-list-item-avatar size="25">
              <v-img :alt="`${name} avatar`" :src="avatar"></v-img>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title v-text="name"></v-list-item-title>
            </v-list-item-content>
            <v-icon v-if="notification === 'notification'" color="blue">{{
              "mdi-circle-small"
            }}</v-icon>
            <v-icon v-if="notification === 'live'" color="#f00" size="20">{{
              "mdi-access-point"
            }}</v-icon>
          </v-list-item>
          <div v-if="!showMoreSubscriptions">
            <v-list-item
              link
              @click.stop="showMoreSubscriptions = !showMoreSubscriptions"
            >
              <v-list-item-icon class="mr-4">
                <v-icon color="grey">{{ "mdi-chevron-down" }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title
                  >Kuva veel {{ more_subscriptions.length }}</v-list-item-title
                >
              </v-list-item-content>
            </v-list-item>
          </div>
          <div v-else>
            <v-list-item
              v-for="[avatar, name, notification] in subscriptions"
              :key="avatar"
              link
            >
              <v-list-item-avatar size="25">
                <v-img :alt="`${name} avatar`" :src="avatar"></v-img>
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title v-text="name"></v-list-item-title>
              </v-list-item-content>
              <v-icon v-if="notification === 'notification'" color="blue">{{
                "mdi-circle-small"
              }}</v-icon>
              <v-icon v-if="notification === 'live'" color="#f00" size="20">{{
                "mdi-access-point"
              }}</v-icon>
            </v-list-item>
            <v-list-item
              link
              @click.stop="showMoreSubscriptions = !showMoreSubscriptions"
            >
              <v-list-item-icon class="mr-4">
                <v-icon color="grey">{{ "mdi-chevron-up" }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>Näita vähem</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </div>
        </v-list>
        <v-divider></v-divider>
        <v-list nav dense>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-subtitle>
                ROHKEM YOUTUBE'IST
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-list-item v-for="[icon, text] in links_more" :key="icon" link>
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
          <v-list-item v-for="[icon, text] in links_more2" :key="icon" link>
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
              <p>aa</p>
              <p>aa</p>
              <p>aa</p>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </div>
    </v-navigation-drawer>

    <v-app-bar :clipped-left="clipped" fixed app flat class="grey darken-4">
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
      <v-img
        class="mx-2"
        src="https://www.youtube.com/about/static/svgs/icons/brand-resources/YouTube-logo-full_color_dark.svg"
        max-height="80"
        max-width="90"
        contain
      ></v-img>
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
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
  data() {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      showMoreSubscriptions: false,
      title: "Youtube",
      cards: ["Today", "Yesterday"],
      links_mini: [
        ["mdi-home", "Avaleht"],
        ["mdi-fire", "Populaarsed"],
        ["mdi-youtube-subscription", "Tellimused"],
        ["mdi-play-box-multiple", "Kogu"]
      ],
      links_main: [
        ["mdi-home", "Avaleht"],
        ["mdi-fire", "Populaarsed"],
        ["mdi-youtube-subscription", "Tellimused"]
      ],
      links_secondary: [
        ["mdi-play-box-multiple", "Kogu"],
        ["mdi-history", "Ajalugu"],
        ["mdi-play-box-outline", "Teie videod"],
        ["mdi-clock", "Hiljem vaatamiseks"],
        ["mdi-playlist-play", "Lemmikud"],
        ["mdi-thumb-up", "Meeldinud videod"]
      ],
      links_more: [
        ["mdi-youtube", "YouTube Premium"],
        ["mdi-youtube-gaming", "Mängud"],
        ["mdi-access-point", "Otseülekanded"],
        ["mdi-trophy", "Sport"]
      ],
      links_more2: [
        ["mdi-cog", "Seaded"],
        ["mdi-flag", "Teavituste ajalugu"],
        ["mdi-help-circle", "Abi"],
        ["mdi-message-alert", "Saada tagasisidet"]
      ],
      subscriptions: [
        [
          "https://yt3.ggpht.com/ytc/AAUvwniGuwmwnYd63hDKeebvj4KBUBvouY3FtszqSRMrYw=s88-c-k-c0x00ffffff-no-rj",
          "Sidemen",
          "live"
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwninLx6_ZEJLBDLKYaB-9KMKLb5aQOoFUC_cx-Kz=s88-c-k-c0x00ffffff-no-rj",
          "SidemenReacts",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwniVxsVsLQpT-pOCm1CpW1sG5PkFRBbAe4jExlSClg=s88-c-k-c0x00ffffff-no-rj",
          "MoreSidemen",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnjbH0uVPRm82votoF1QMjuJbudQvTJjrR_cBOYyog=s88-c-k-c0x00ffffff-no-rj",
          "SwaggerSouls",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnipIOGF5oWVbSffcVHhvJm5guRr4A21wbbmy1NX=s88-c-k-c0x00ffffff-no-rj",
          "LEMMiNO",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnj4Nx2WoQcBF-mPsUhE8H4Xvvasx17DwhJ14MzQ3Q=s88-c-k-c0x00ffffff-no-rj",
          "Pyrocynical",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnhKr-KpJ_6VZDp1UHjpfnEjIQYQnxKQNMUg3WCMiw=s88-c-k-c0x00ffffff-no-rj",
          "Callux",
          "notification"
        ]
      ],
      more_subscriptions: [
        [
          "https://yt3.ggpht.com/ytc/AAUvwniGuwmwnYd63hDKeebvj4KBUBvouY3FtszqSRMrYw=s88-c-k-c0x00ffffff-no-rj",
          "Sidemen",
          "live"
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwninLx6_ZEJLBDLKYaB-9KMKLb5aQOoFUC_cx-Kz=s88-c-k-c0x00ffffff-no-rj",
          "SidemenReacts",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwniVxsVsLQpT-pOCm1CpW1sG5PkFRBbAe4jExlSClg=s88-c-k-c0x00ffffff-no-rj",
          "MoreSidemen",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnjbH0uVPRm82votoF1QMjuJbudQvTJjrR_cBOYyog=s88-c-k-c0x00ffffff-no-rj",
          "SwaggerSouls",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnipIOGF5oWVbSffcVHhvJm5guRr4A21wbbmy1NX=s88-c-k-c0x00ffffff-no-rj",
          "LEMMiNO",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnj4Nx2WoQcBF-mPsUhE8H4Xvvasx17DwhJ14MzQ3Q=s88-c-k-c0x00ffffff-no-rj",
          "Pyrocynical",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AAUvwnhKr-KpJ_6VZDp1UHjpfnEjIQYQnxKQNMUg3WCMiw=s88-c-k-c0x00ffffff-no-rj",
          "Callux",
          "notification"
        ]
      ]
    };
  }
};
</script>
<style>
.v-navigation-drawer__content::-webkit-scrollbar {
  width: 8px;
  background-color: #212121;
}

.v-navigation-drawer__content::-webkit-scrollbar-thumb {
  background: #616161;
}

.v-list-item-icon__content {
  display: flex;
  flex-direction: column;
}
</style>
