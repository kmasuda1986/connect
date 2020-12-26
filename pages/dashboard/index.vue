<template>
  <v-row class="flex-child justify-center">
    <v-col cols="12" md="6" sm="8">
      <v-card>
        <v-card-text>
          test
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  layout: 'dashboard/default',
  data: () => ({
    valid: true,
    user: {
      email: '',
      password: ''
    }
  }),
  methods: {
    login () {
      //
    }
  }
}
</script>
