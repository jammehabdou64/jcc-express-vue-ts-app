<template>
  <Head>
    <title>Register</title>
    <meta name="description" content="Your page description" />
  </Head>
  <Header />
  <div
    class="container mx-auto flex items-center justify-center min-h-[calc(100vh-4rem)] py-12"
  >
    <div
      class="rounded-xl border bg-card text-card-foreground shadow w-full max-w-md"
    >
      <div class="flex flex-col space-y-1.5 p-6">
        <div class="font-semibold tracking-tight text-2xl">
          Create an account
        </div>
        <div class="text-sm text-muted-foreground">
          Enter your information to create an account
        </div>
      </div>
      <form @submit.prevent="submit">
        <div class="p-6 pt-0 space-y-4">
          <div class="space-y-2">
            <label class="input-label" for="name">Name</label
            ><input
              class="form-control"
              id="name"
              placeholder="John Doe"
              v-model="form.name"
              required
            />
            <small v-if="form?.errors?.name" class="text-sm text-red-500">
              {{ form?.errors?.name }}</small
            >
          </div>
          <div class="space-y-2">
            <label class="input-label" for="email">Email</label
            ><input
              class="form-control"
              id="email"
              placeholder="name@example.com"
              required
              type="email"
              v-model="form.email"
            />
            <small v-if="form?.errors?.email" class="text-sm text-red-500">
              {{ form?.errors?.email }}</small
            >
          </div>
          <div class="space-y-2">
            <label class="input-label" for="password">Password</label
            ><input
              class="form-control"
              id="password"
              required
              type="password"
              v-model="form.password"
            />
            <small v-if="form?.errors?.password" class="text-sm text-red-500">
              {{ form?.errors?.password }}</small
            >
          </div>
          <div class="space-y-2">
            <label class="input-label" for="confirm-password"
              >Confirm Password</label
            ><input
              class="form-control"
              id="confirm-password"
              required
              type="password"
              v-model="form.confirmPassword"
            />
            <small
              v-if="form?.errors?.confirmPassword"
              class="text-sm text-red-500"
            >
              {{ form?.errors?.confirmPassword }}</small
            >
          </div>
        </div>
        <div class="items-center p-6 pt-0 flex flex-col space-y-4">
          <button class="submit-button" type="submit">Register</button>
          <div class="text-center text-sm">
            Already have an account?
            <Link class="text-primary hover:underline" href="/login"
              >Login</Link
            >
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Link, useForm, Head } from "@inertiajs/vue3";
import Header from "@/Components/Header.vue";

const form = useForm({
  name: "",
  email: "",
  password: "",
  confirmPassword: "",
});

const submit = () => {
  form.post("/auth/register");
};
</script>
