<template>
  <v-container>
    <v-row>
      <v-col v-for="(video, n) in videos" :key="n" cols="3" class="mb-5 pl-10">
        <v-hover v-slot="{ hover }" open-delay="500">
          <div>
            <v-row dense
              ><v-img v-if="hover" :src="video.thumbnailwebp" contain></v-img>
              <v-img v-else :src="video.thumbnailjpg" contain></v-img>
            </v-row>
            <v-row class="mt-5" dense>
              <v-col :cols="2" class="pl-0 pr-0">
                <v-avatar size="40">
                  <v-img :src="video.avatar"></v-img> </v-avatar
              ></v-col>
              <v-col :cols="10" class="pl-0">
                <v-list-item-title
                  class="font-weight-bold"
                  style="white-space: pre-wrap; margin-bottom: -20px;"
                  >{{ video.title }}
                </v-list-item-title>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.channelName }}
                  <v-icon color="grey" size="14" class="ml-1">{{
                    "mdi-check-circle"
                  }}</v-icon>
                </v-list-item-subtitle>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.views }}
                  <v-icon color="grey" size="20" class="ml-0 mr-0">{{
                    "mdi-circle-small"
                  }}</v-icon>
                  {{ video.date }}
                </v-list-item-subtitle></v-col
              >
            </v-row>
          </div>
        </v-hover>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      videos: [
        {
          title: "W2S once stuck a carrot up his bum",
          channelName: "W2SClips",
          views: "82 tuh vaatamist",
          date: "12 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/DUpxo_mgb2E/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLDpSqxz3AYnfqTzinsPc-MNn-9d1A",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/DUpxo_mgb2E/mqdefault_6s.webp?du=3000&sqp=CMqo04IG&rs=AOn4CLAYzIxmiR6nH-CM_z55OrJEI245bw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnivJQdsEtMFvt5Hqf9AaUvBY14YNNmLsezA_KLu=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "The World Strongest Family...",
          channelName: "PewDiePie",
          views: "257 tuh vaatamist",
          date: "28 minuti eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/gICHHgfB36s/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLCAMMsymNmswyuNqfLPy-9d0SBPeA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gICHHgfB36s/mqdefault_6s.webp?du=3000&sqp=CLyJ04IG&rs=AOn4CLAmw7FZYqnu6dzMw5ptdsrrO26vvw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnjF74vH7EMiv2CT3s8LUz80hujPthpGw0D-5sizAg=s68-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Top Scary Coincidences in History",
          channelName: "SidemenReacts",
          views: "127 tuh vaatamist",
          date: "39 minuti eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/qRnrofE95LQ/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLDb8_7eZHsasZz5I7Dnt4wKmn_Dgw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/qRnrofE95LQ/mqdefault_6s.webp?du=3000&sqp=CIy904IG&rs=AOn4CLDmpyL-fHtIg1L_xIxbmkrKjYJ9xw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwninLx6_ZEJLBDLKYaB-9KMKLb5aQOoFUC_cx-Kz=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "W2S gets annoyed by a massive donation",
          channelName: "W2SClips",
          views: "41 tuh vaatamist",
          date: "1 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/hVL3uYrSa0I/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLB5gsiXVre0QFTVyq-KymvhsjbUuQ",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/hVL3uYrSa0I/mqdefault_6s.webp?du=3000&sqp=CKS704IG&rs=AOn4CLAS3fy-8HguJiaWo5zgaDk_vWRWCA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnivJQdsEtMFvt5Hqf9AaUvBY14YNNmLsezA_KLu=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "So Many MISERABLY FAILED LED Lights",
          channelName: "ElectroBOOM",
          views: "83 tuh vaatamist",
          date: "1 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/lIK1jnYr0yw/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLAqRV-bWp0LBxab-XPatBdzBWldFA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/lIK1jnYr0yw/mqdefault_6s.webp?du=3000&sqp=COyH04IG&rs=AOn4CLDyrWJQx_BO30r-2O6vY1ai-M9ssg",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnjXowqOpksZocsdozpm35jX45Sox5z9NHsM_k5PyQ=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "W2S gets swatted live on stream (Hard to watch)",
          channelName: "W2SClips",
          views: "108 tuh vaatamist",
          date: "18 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/1YJmBakHc3w/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLCMi4OioB82uDFZffAYxdYMYLFZtw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/1YJmBakHc3w/mqdefault_6s.webp?du=3000&sqp=CPzJ04IG&rs=AOn4CLCJA4ZOSo86hOyDGWXSBzaE8mOCnw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnivJQdsEtMFvt5Hqf9AaUvBY14YNNmLsezA_KLu=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Glitterbomb Trap Catches Phone Scammer (who gets arrested)",
          channelName: "Mark Rober",
          views: "6,6 mln vaatamist",
          date: "23 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/VrKW58MS12g/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLBchokdwsxSkikaHE-9vk1g-dyg8g",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/VrKW58MS12g/mqdefault_6s.webp?du=3000&sqp=CKDB04IG&rs=AOn4CLB9NHkPo3NJL8gIN4bz--IzuRBZqA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnhL2suWx4XHAshVXnSqPdXWHR_kQV_m1bkxDJw=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: 'Top "What Could Go Wrong" Fails',
          channelName: "SidemenReacts",
          views: "1 mln vaatamist",
          date: "1 päeva eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/6MIIvoNWzL0/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLA-k4A-tQuXWgj-bY11GPfEFwcOIA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/6MIIvoNWzL0/mqdefault_6s.webp?du=3000&sqp=CLe304IG&rs=AOn4CLCa2xd9KOcu_EjVhnc_ZRfMuxH9tA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwninLx6_ZEJLBDLKYaB-9KMKLb5aQOoFUC_cx-Kz=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Logan Paul's first movie is worse than you can imagine",
          channelName: "Pyrocynical",
          views: "1,1 mln vaatamist",
          date: "1 päeva eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/3HOuBTGabI4/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLAr1gI3iVKKz3bLMmgmDBJWL9x-JQ",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/3HOuBTGabI4/mqdefault_6s.webp?du=3000&sqp=CK6H04IG&rs=AOn4CLArdbY-PDHpzAvUt9zZdtXR_ETi-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnj4Nx2WoQcBF-mPsUhE8H4Xvvasx17DwhJ14MzQ3Q=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title:
            "Buying Scotland to 1 UP Mr Beast - FREE LAND IS PERFECTLY BALANCED WITH NO EXPLOITS",
          channelName: "The Spiffing Brit",
          views: "618 tuh vaatamist",
          date: "1 päeva eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/mAySKo0s27g/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLCUNoJjsJY1L4Djo7kKs6wkcGE5_Q",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/mAySKo0s27g/mqdefault_6s.webp?du=3000&sqp=CKir04IG&rs=AOn4CLDigFisk5uIx8rZmawafiH_AzI_4g",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnixkIe7mdcrEaWxOYDAwm4XXilct2oTNG5d5AYYlw=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Behzinga Uses the Forbidden Towel",
          channelName: "SidemenShorts",
          views: "38 tuh vaatamist",
          date: "2 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/BbkoV0C12PU/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLDL3qzBK1xI1z49Uj7jiVTo2Mmf2A",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/BbkoV0C12PU/mqdefault_6s.webp?du=3000&sqp=COSx04IG&rs=AOn4CLBQuG_q_zqoz_djx91knojuQnXUuA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnhFTXDbvii0YojFlEuSsrZQVsDLNIcsIBKGxBWy=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "GUARANTEED PRIME ICON PACKS GOT ME THIS...",
          channelName: "MiniminterClips",
          views: "18 tuh vaatamist",
          date: "3 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/uJbB1LVPMNs/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLDo_ih-ECzWx7_J_1sFihpK_sl9Jg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/uJbB1LVPMNs/mqdefault_6s.webp?du=3000&sqp=CPbG04IG&rs=AOn4CLCVL4Kund57kF6qOnQhA8JBosxQBw",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwng1rg88LX1mxZE2Po7kAWvXES3GncQMwp2lzVjx=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "W2S speaks fluent Arabic",
          channelName: "W2SClips",
          views: "39 tuh vaatamist",
          date: "4 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/OqTKMrgacCc/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLBk7BjQnJ_zbMNv58yKRmE_lWmzzw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/OqTKMrgacCc/mqdefault_6s.webp?du=3000&sqp=CPnP04IG&rs=AOn4CLCo1pxdF3Hh_8Zj6iBTHykm57szMA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnivJQdsEtMFvt5Hqf9AaUvBY14YNNmLsezA_KLu=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title:
            "Hoi4 MP In A Nutshell Full Episodes #182(The Great Purge Part 1)",
          channelName: "Bokoen1",
          views: "43 tuh vaatamist",
          date: "17 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/kyg4Mt5NP94/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLCxNqNpQU4iKeEzzqsMKNAROOz57g",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/kyg4Mt5NP94/mqdefault_6s.webp?du=3000&sqp=CJLN04IG&rs=AOn4CLA32q681jWXhJ8lxPZZ-yBOJOTsMg",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnjkq8MiLkcq1ygNmkWfLk8v-YJNRrTWTtDPxjDN=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "SIDEMEN HIDE AND SEEK IN GTA 5",
          channelName: "MoreSidemen",
          views: "1,7 mln vaatamist",
          date: "23 tunni eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/jCr29oI727M/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLCzmTx0bm5Mg4C_HZTIBQ0gdITr1w",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/jCr29oI727M/mqdefault_6s.webp?du=3000&sqp=CNe904IG&rs=AOn4CLBZ2qw5q7-g4JKOME17c8lo7TgfHA",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwniVxsVsLQpT-pOCm1CpW1sG5PkFRBbAe4jExlSClg=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Everything We Don't Know",
          channelName: "Aperture",
          views: "633 vaatamist",
          date: "3 minuti eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/h667P20VFO4/hqdefault.jpg?sqp=-oaymwEbCNIBEHZIVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLAHGMR4506PdGCqYOtaZtmWFjnhWA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/h667P20VFO4/mqdefault_6s.webp?du=3000&sqp=CM6y04IG&rs=AOn4CLCXNRnt79iufC67QZbhoYlZfQ3Syg",
          avatar:
            "https://yt3.ggpht.com/ytc/AAUvwnhoyqnBWkgK9hg5grq_5ZhDlCuWlEv8uObllBhDow=s88-c-k-c0x00ffffff-no-rj"
        }
      ]
    };
  }
};
</script>
