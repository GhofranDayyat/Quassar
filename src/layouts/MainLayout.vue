<template>
  <q-layout view="lHh Lpr lFf">
    <q-page-container>
      <q-page
        v-if="showOriginalContent"
        @click="showOriginalContent = false"
        class="flex flex-center"
      >
        <div class="row">
          <div class="column">
            <div class="q-pa-md">
              <p class="logo-text">هيئة الهلال الاحمر السعودي</p>
              <p>Saudi Red Crescent Authority</p>
            </div>
          </div>
          <img
            :src="logo"
            spinner-color="white"
            fit="contain"
            style="width: 60px; height: 70px"
          />
        </div>
      </q-page>
      <router-view v-else />
    </q-page-container>
  </q-layout>
</template>

<style scoped>
.logo-text {
  margin-bottom: 0;
  display: flex;
  flex-direction: row-reverse;
  font-size: 20px;
}
</style>
<script lang="ts">
import logo from '../assets/logo.png';
export default {
  name: 'MainLayout',
  data() {
    return {
      logo: logo,
      showOriginalContent: true,
    };
  },
};
</script>
