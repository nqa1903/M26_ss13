<template>
  <div>
    <p>Câu 4</p>
    <v-menu>
      <template v-slot:activator="{ props }">
        <v-btn color="primary" v-bind="props"> Quản trị viên </v-btn>
      </template>
      <v-list>
        <v-list-item v-for="(item, index) in items" :key="index" :value="index">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script setup>
import { ref } from "vue";

const items = ref([
  { title: "Thông tin cá nhân" },
  { title: "Đổi mật khẩu" },
  { title: "Đăng xuất" },
]);
</script>

<style scoped></style>
