<template>
  <v-app>
    <v-navigation-drawer app v-model="drawer" clipped>
      <v-container>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="title grey--text text--darken-2">メニュー</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-divider></v-divider>
      </v-container>
      <v-list nav dense>
        <v-list-item-group>
          <v-list-item v-for="nav_list in nav_lists" :key="nav_list.name" :to="nav_list.link">
            <v-list-item-icon>
              <v-icon>{{ nav_list.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{ nav_list.name }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar color="light-blue accent-2" dark app clipped-left>
      <v-app-bar-nav-icon @click="drawer=!drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-h4">パワフェス経験値計算 〜Pawafes point Calculator 2021〜</v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- <v-btn outlined><a href="https://twitter.com/share?ref_src=twsrc%5Etfw" class="twitter-share-button" data-show-count="false">Tweet</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script></v-btn> -->
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>

    <v-footer color="light-blue accent-2" dark app>
      &copy;パワフェス計算ツール
    </v-footer>
  </v-app>
</template>

<script>

export default {

  data: () => ({
    drawer: null,
    nav_lists: [
      {
        name: 'ホーム',
        icon: 'mdi-home',
        link: '/'
      },
      {
        name: 'お知らせ',
        icon: 'mdi-alert-circle',
        link: '/announce'
      },
      {
        name: 'プライバシーポリシー',
        icon: 'mdi-card-text',
        link: '/policy'
      },
      {
        name: 'フィードバックを送信',
        icon: 'mdi-message-alert',
        link: '/feedback'
      }
    ]
  }),
};
</script>
