<template>
  <v-card title="SSO 구현해보기" subtitle="OIDC & OAuth2.0"
    text="Access Token과 ID Token을 얻어서 뿌릴 수 있어야 한다. 회원가입 및 로그인, 로그아웃과 같은 동작이 가능해야한다.">
    <v-card-actions>
      <v-btn @click="login" prepend-icon="mdi-login">LOGIN</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
import axios from "axios";

export default {
  methods: {
    login() {
      alert("LOGIN BUTTON");
      axios.get('http://localhost:3000/auth/login')
        .then(response => {
          // Express 백엔드로 리디렉션된 후에는 인증 서비스에서 로그인을 수행합니다.
          alert(response);
        })
        .catch(error => {
          alert(error);
        });
    }
  }
};
</script>