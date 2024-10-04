<template>
  <p>Câu 9</p>
  <form @submit.prevent="submit">
    <v-text-field
      v-model="name.value.value"
      :counter="10"
      :error-messages="name.errorMessage.value"
      label="Name"
    ></v-text-field>

    <v-text-field
      v-model="company.value.value"
      :counter="10"
      :error-messages="company.errorMessage.value"
      label="Company"
    ></v-text-field>

    <v-text-field
      v-model="email.value.value"
      :error-messages="email.errorMessage.value"
      label="E-mail"
    ></v-text-field>

    <v-text-field
      v-model="phone.value.value"
      :counter="7"
      :error-messages="phone.errorMessage.value"
      label="Phone No"
    ></v-text-field>

    <v-textarea label="Message" clearable></v-textarea>

    <v-btn class="me-4" type="submit"> submit </v-btn>

  </form>
</template>

<script setup>
import { ref } from "vue";
import { useField, useForm } from "vee-validate";

const { handleSubmit, handleReset } = useForm({
  validationSchema: {
    name(value) {
      if (value?.length >= 2) return true;

      return "Name needs to be at least 2 characters.";
    },
    company(value) {
      if (/^[0-9-]{10,}$/.test(value)) return true;

      return "Company name needs to be at least 10 digits.";
    },
    phone(value) {
      if (/^[0-9-]{7,}$/.test(value)) return true;

      return "Phone number needs to be at least 7 digits.";
    },
    email(value) {
      if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true;

      return "Must be a valid e-mail.";
    },
  },
});
const name = useField("name");
const company = useField("company");
const phone = useField("phone");
const email = useField("email");

const submit = handleSubmit((values) => {
  alert(JSON.stringify(values, null, 2));
});
</script>

<style scoped></style>
