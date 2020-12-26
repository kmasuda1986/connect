<template>
  <v-app>
    <v-app-bar
      color="indigo"
      app
      dark
      flat
    >
      <v-toolbar-title v-text="title" />
    </v-app-bar>
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
    title: 'Connect'
  })
}
</script>

<style lang="scss">
.main {
  background-color: #E6E6E6;
}
</style>
