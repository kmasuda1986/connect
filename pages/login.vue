<template>
  <v-row class="flex-child justify-center">
    <v-col cols="12" md="6" sm="8">
      <v-card>
        <v-card-text>
          <v-row class="justify-center py-10">
            <v-col cols="12" class="mb-8 text-center">
              <h1>
                ようこそ！
              </h1>
            </v-col>
            <v-col cols="12" md="10" sm="10">
              <v-form
                ref="form"
                v-model="valid"
                @submit.prevent="login"
              >
                <v-text-field
                  v-model="user.email"
                  label="メールアドレス"
                  outlined
                  required
                />
                <v-text-field
                  v-model="user.password"
                  label="パスワード"
                  outlined
                  required
                />
                <v-btn
                  color="primary"
                  type="submit"
                  block
                  dark
                  depressed
                  large
                  tile
                >
                  ログイン
                </v-btn>
              </v-form>
              <v-divider class="my-10" />
              <v-btn
                class="body-1 my-3"
                block
                text
              >
                アカウント新規作成はこちら
              </v-btn>
              <v-btn
                class="body-1"
                block
                text
              >
                パスワードを忘れた方はこちら
              </v-btn>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
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
