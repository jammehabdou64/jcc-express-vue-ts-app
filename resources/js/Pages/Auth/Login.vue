<template>
  <Head>
    <title>Login</title>
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
        <div class="font-semibold tracking-tight text-2xl">Login</div>
        <div class="text-sm text-muted-foreground">
          Enter your credentials to access your account
        </div>
      </div>

      <form @submit.prevent="submit">
        <div class="p-6 pt-0 space-y-4">
          <div class="space-y-2">
            <label class="input-label" for="email">Email</label
            ><input
              class="form-control"
              id="email"
              placeholder="name@example.com"
              required
              v-model="form.email"
              type="email"
              name="email"
            />
            <small v-if="form?.errors?.email" class="text-sm text-red-500">
              {{ form?.errors?.email }}</small
            >
          </div>
          <div class="space-y-2">
            <div class="flex items-center justify-between">
              <label class="input-label" for="password">Password</label
              ><a
                class="text-sm text-primary hover:underline"
                href="/auth/forgot-password"
                >Forgot password?</a
              >
            </div>
            <input
              class="form-control"
              id="password"
              required
              v-model="form.password"
              type="password"
              name="password"
            />
          </div>
        </div>
        <div class="items-center p-6 pt-0 flex flex-col space-y-4">
          <button
            class="submit-button"
            type="submit"
            :disabled="form?.processing"
          >
            {{ form?.processing ? "Logging in..." : "Login" }}
          </button>
          <div class="text-center text-sm">
            Don't have an account?
            <Link class="text-primary hover:underline" href="/register"
              >Register</Link
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
  email: "",
  password: "",
});

const submit = () => {
  form.post("/auth/login");
};
</script>
