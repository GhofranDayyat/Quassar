<template>
  <q-page-container class="container d-flex flex-column j-between align-center">
    <q-img :src="logo" width="112px" height="127px" />
    <q-page-container :style="{ width: '90%' }">
      <div class="d-flex flex-column align-end">
        <p :style="{ fontSize: '20px' }">إبـدأ الأن</p>
        <p :style="{ fontSize: '16px' }">قم بتسجيل الدخول للمتابعة</p>
      </div>

      <q-form @submit.prevent="onSubmit" class="q-gutter-md" :valid="valid">
        <q-input
          filled
          v-model="username"
          label="اسم المستخدم"
          lazy-rules
          style="direction: rtl"
          reverse
          :rules="[(val) => (val && val.length) || 'الرجاء كتابة شيء ما']"
        >
          <template v-slot:append>
            <!-- <q-icon style="margin: 0 220px 0 0" /> -->
          </template>
        </q-input>
        <q-input
          filled
          v-model="password"
          label="ادخل كلمة المرور"
          lazy-rules
          append-inner-style
          hint="نسيـت كلمة المرور؟"
          style="direction: rtl"
          :rules="[(val) => (val && val.length) || 'الرجاء كتابة شيء ما']"
          :type="isPwd ? 'password' : 'text'"
        >
          <template v-slot:append>
            <q-icon
              :name="isPwd ? 'visibility_off' : 'visibility'"
              class="cursor-pointer"
              @click="isPwd = !isPwd"
            />
          </template>
        </q-input>
      </q-form>
    </q-page-container>
    <q-btn
      type="submit"
      color="#C00"
      @click="onSubmit"
      label="تسجيـل الدخــول"
      class="login-btn"
    />
  </q-page-container>
</template>

<style scoped>
.container {
  height: 68vh;
  margin-top: 50%;
}
.login-btn {
  width: 100%;
  background-color: #c00;
  margin-bottom: 20px;
  border-radius: 16px;
  width: 90%;
  height: 56px;
  align-self: center;
  font-size: 16px;
}
</style>

<script lang="ts">

import logo from '../assets/logo.png';
// const $q = useQuasar();
// import { $q } from 'quasar'



export default {
  name: 'LoginComponent',
  data() {
    return {
      logo,
      password: '',
      username: '',
      isPwd: true,
    };
  },

  methods: {
    onSubmit() {
   
      // console.log($q, '66666');

      // $q.notify('Message');
      // $q.notify({
      //   color: 'negative',
      //   // textColor,
      //   icon: 'report_problem',
      //   message: 'تحقق من اسم المستخدم أو كلمة المرور',
      //   position: 'top',
      // });
    },
   
  },
};
</script>
