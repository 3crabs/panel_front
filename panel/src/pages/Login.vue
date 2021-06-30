<template>
    <q-layout view="lHh lpr lFf" class="flex content-center justify-center">

      <q-page-container class="flex column content-center justify-center" style="padding-bottom: 70px;">
        <div class="main-text q-mb-lg">
          panel`
        </div>

        <div class="form">
          <small>логин</small>
          <q-input class="login q-mb-lg" filled style="border-radius: 6px" v-model="login" :dense="true"/>

          <small>пароль</small>
          <q-input class="password" type="password" filled style="border-radius: 6px" v-model="password" :dense="true" />
          <div class="error-message">
            {{errorMessage}}
          </div>
        </div>

        <div class="q-mt-lg">
          <q-btn class="login-button" unelevated no-caps>
            войти
          </q-btn>
        </div>



      </q-page-container>

    </q-layout>

</template>

<script>
import Header from "../components/LayoutComponents/Header";
export default {
  name: 'Login',
  components: {Header},

  data() {
    return {
      login: "",
      password: "",
      errorMessage: "",
    }
  }
}
</script>

<style scoped>
.login{
  width: 425px;
}
small{
  font-size: 15px;
  text-align: left;
  color: #425466;
}
.login-button{
  background: #F2994A;
  font-family: Inter,sans-serif;
  font-style: normal;
  font-size: 15px;
  line-height: 14px;
  color: white;
  width: 425px;
}
.error-message{
  color: #FF5151;
  height: 12px;
  text-align: center;
  margin-top: 5px;
}
.main-text {
  background: linear-gradient(to top, #F46B45, #EEA849);
  text-align: center;
  font-family: Inter,sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 125px;
  letter-spacing: -0.04em;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>
