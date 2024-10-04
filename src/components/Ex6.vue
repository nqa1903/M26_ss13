<template>
  <div>
    <p>Câu 6</p>
    <v-dialog max-width="400">
      <template v-slot:activator="{ props: activatorProps }">
        <v-btn
          v-bind="activatorProps"
          color="white"
          text="Xác nhận"
          variant="elevated"
        ></v-btn>
      </template>

      <template v-slot:default="{ isActive }">
        <v-card title="Xác nhận">
          <v-card-text>
            Bạn có xác nhận làm mới dữ liệu không ? Nếu có dữ liệu sẽ được cập nhật
          </v-card-text>

          <v-card-actions>
            <v-spacer></v-spacer>

            <v-btn text="Xác nhận" @click="isActive.value = false"></v-btn>
          </v-card-actions>
        </v-card>
      </template>
    </v-dialog>
  </div>
</template>

<script setup></script>

<style scoped></style>
