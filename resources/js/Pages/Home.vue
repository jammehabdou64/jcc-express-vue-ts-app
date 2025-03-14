<template>
  <Head>
    <title>Welcome</title>
    <meta name="description" content="Your page description" />
  </Head>
  <div>Welcome: {{ auth?.name }}</div>
</template>
<script setup lang="ts">
import { usePage, Head } from "@inertiajs/vue3";
const auth = usePage().props?.auth;
</script>
