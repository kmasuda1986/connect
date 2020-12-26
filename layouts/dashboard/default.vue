<template>
  <v-app>
    <v-app-bar
      color="indigo"
      app
      dark
      flat
    >
      <v-app-bar-nav-icon
        @click="drawer = true"
      />
      <v-toolbar-title
        v-text="title"
      />
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list>
        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title class="title">
              {{ user.name }}
            </v-list-item-title>
            <v-list-item-subtitle>sandra_a88@gmail.com</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-list
        nav
        dense
      >
        <div v-for="page in pages" :key="page.id">
          <v-list-item @click="goNextPage(page.path)">
            <v-list-item-icon>
              <v-icon
                color="indigo lighten-1"
              >
                {{ page.icon }}
              </v-icon>
            </v-list-item-icon>
            <v-list-item-title>
              {{ page.name }}
            </v-list-item-title>
          </v-list-item>
        </div>
      </v-list>
    </v-navigation-drawer>
    <v-main class="main">
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <custom-footer />
  </v-app>
</template>

<script>
export default {
  components: {
    CustomFooter: () => import('@/components/CustomFooter')
  },
  data: () => ({
    drawer: false,
    group: null,
    title: 'Connect',
    pages: [
      {
        id: 1,
        icon: 'mdi-home',
        name: 'ダッシュボード',
        path: '/dashboard'
      },
      {
        id: 2,
        icon: 'mdi-account',
        name: '自分の情報',
        path: '/dashboard/myprofile'
      },
      {
        id: 3,
        icon: 'mdi-exit-run',
        name: 'ログアウト',
        path: '/login'
      }
    ],
    user: {
      name: '増田健太郎'
    }
  }),
  methods: {
    goNextPage (path) {
      this.$router.push(path)
    }
  }
}
</script>

<style lang="scss">
.main {
  background-color: #E6E6E6;
}
</style>
