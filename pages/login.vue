<template>
  <v-form>
    <v-container>
      <v-text-field label="MailAddress" v-model="mail"></v-text-field>
      <v-text-field label="Password" v-model="pass"></v-text-field>
      <v-btn color="primary" @click="login">ログイン</v-btn>
    </v-container>
  </v-form>
</template>

<script>
</script>
