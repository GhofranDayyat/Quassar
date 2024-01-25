<template>
  <q-page-container>
    <div class="lang-row">
      <q-btn flat no-wrap label="English" padding="10px 20px">
        <q-icon name="language" class="icon"
      /></q-btn>
    </div>
  </q-page-container>
</template>

<style scoped>
.lang-row {
  display: flex;
  flex-direction: row-reverse;
  margin: 10px;
}

.icon {
  background-color: #c00;
  border-radius: 50%;
  color: white;
  padding: 8px;
  margin: 0 5%;
}
</style>

<script lang="ts">
export default {
  name: 'HeaderComponent',
};
</script>
