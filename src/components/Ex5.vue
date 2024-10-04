<template>
  <p>Câu 5</p>
  <div class="w">
    <v-alert
      v-model="alert"
      close-label="Close Alert"
      color="gray"
      title="Xác nhận"
      variant="tonal"
      width="400"
      closable
    >
      Bạn có chắc chắn muốn xóa tài khoản ?
    </v-alert>

    <div v-if="!alert" class="text-center">
      <v-btn @click="alert = true">Reset</v-btn>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const alert = ref(true);
</script>

<style scoped>
.w {
  width: 400px !important;
}
</style>
