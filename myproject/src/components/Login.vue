<template>
  <v-app>
  <div class="container">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1>ログイン画面</h1>
    <br>
    <label for="mail">メールアドレス</label>
    <input type="text" id="mail" placeholder="E-mail" v-model="email">
    <br>
    <label for="password">パスワード</label>
    <input type="password" id="password" placeholder="Password" v-model="password">
    <br><br>
    <v-btn color="blue" outlined @click="login">ログイン</v-btn>
    <br>
    <router-link to="./Register">新規登録はこちらから</router-link>
  </div>
  </v-app>
</template>
<script>
export default {
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login() {
      this.$store.dispatch('login', {email: this.email, password: this.password})
    }
  }
}
</script>
<style scoped>
.container {
  margin-left: 600px;
}
label {
  margin-right: 10px;
  width: 120px;
  float: left;
}
button {
  margin-left: 40px;
}
</style>