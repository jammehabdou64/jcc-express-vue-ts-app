<template>
  <Head>
    <title>Welcome</title>
    <meta name="description" content="Your page description" />
  </Head>
  <Header />
  <div class="flex flex-col min-h-screen">
    <!--  Hero Section  -->
    <section
      class="w-full py-12 md:py-24 lg:py-32 xl:py-48 bg-gradient-to-b from-background to-muted"
    >
      <div class="container mx-auto px-4 md:px-6">
        <div class="flex flex-col items-center space-y-4 text-center">
          <div class="space-y-2">
            <h1
              class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl lg:text-6xl"
            >
              JCC Framework Simplified
            </h1>
            <p class="mx-auto max-w-[700px] text-muted-foreground md:text-xl">
              A powerful, lightweight framework built on top of Express.js for
              faster development and better performance.
            </p>
          </div>
          <div class="space-x-4">
            <Link href="/register">
              <Button>
                Get Started
                <ArrowRightIcon class="ml-2 h-4 w-4" />
              </Button>
            </Link>
            <a
              href="https://github.com/jammehabdou64/new-jcc-express-mvc-app"
              target="_blank"
            >
              <Button variant="outline" size="lg" class="secondary-button">
                Documentation
              </Button>
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section  -->
    <section class="w-full py-12 md:py-24 lg:py-32 bg-background">
      <div class="container mx-auto px-4 md:px-6">
        <div
          class="flex flex-col items-center justify-center space-y-4 text-center"
        >
          <div class="space-y-2">
            <h2
              class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl"
            >
              Key Features
            </h2>
            <p class="mx-auto max-w-[700px] text-muted-foreground md:text-xl">
              Everything you need to build modern web applications
            </p>
          </div>
        </div>
        <div
          class="mx-auto grid max-w-5xl grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3 mt-12"
        >
          <div
            class="flex flex-col items-center space-y-2 rounded-lg border p-6 shadow-sm"
          >
            <ServerIcon class="h-12 w-12 text-primary" />
            <h3 class="text-xl font-bold">Express Integration</h3>
            <p class="text-center text-muted-foreground">
              Seamlessly built on top of Express.js with enhanced features and
              simplified APIs.
            </p>
          </div>
          <div
            class="flex flex-col items-center space-y-2 rounded-lg border p-6 shadow-sm"
          >
            <LockClosedIcon class="h-12 w-12 text-primary" />
            <h3 class="text-xl font-bold">Authentication</h3>
            <p class="text-center text-muted-foreground">
              Built-in authentication system with secure user management.
            </p>
          </div>
          <div
            class="flex flex-col items-center space-y-2 rounded-lg border p-6 shadow-sm"
          >
            <CircleStackIcon class="h-12 w-12 text-primary" />
            <h3 class="text-xl font-bold">Database Abstraction</h3>
            <p class="text-center text-muted-foreground">
              Simple database integration with ORM-like features.
            </p>
          </div>
          <div
            class="flex flex-col items-center space-y-2 rounded-lg border p-6 shadow-sm"
          >
            <CodeBracketIcon class="h-12 w-12 text-primary" />
            <h3 class="text-xl font-bold">Middleware System</h3>
            <p class="text-center text-muted-foreground">
              Enhanced middleware system for better request handling.
            </p>
          </div>
          <div
            class="flex flex-col items-center space-y-2 rounded-lg border p-6 shadow-sm"
          >
            <svg
              class="h-12 w-12 text-primary"
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              strokeWidth="2"
              strokeLinecap="round"
              strokeLinejoin="round"
            >
              <path
                d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"
              />
            </svg>
            <h3 class="text-xl font-bold">Performance Optimized</h3>
            <p class="text-center text-muted-foreground">
              Optimized for high performance and low latency applications.
            </p>
          </div>
          <div
            class="flex flex-col items-center space-y-2 rounded-lg border p-6 shadow-sm"
          >
            <svg
              class="h-12 w-12 text-primary"
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              strokeWidth="2"
              strokeLinecap="round"
              strokeLinejoin="round"
            >
              <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10" />
            </svg>
            <h3 class="text-xl font-bold">Security First</h3>
            <p class="text-center text-muted-foreground">
              Built with security best practices to protect your applications.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section  -->
    <section class="w-full py-12 md:py-24 lg:py-32 bg-muted">
      <div class="container mx-auto px-4 md:px-6">
        <div
          class="flex flex-col items-center justify-center space-y-4 text-center"
        >
          <div class="space-y-2">
            <h2
              class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl"
            >
              Ready to Get Started?
            </h2>
            <p class="mx-auto max-w-[700px] text-muted-foreground md:text-xl">
              Join thousands of developers building with our framework.
            </p>
          </div>
          <div class="space-x-4">
            <Link href="/register">
              <Button class="primary-button">
                Sign Up Now
                <ArrowRightIcon class="ml-2 h-4 w-4" />
              </Button>
            </Link>
            <Link href="/login">
              <Button variant="outline" size="lg" class="secondary-button"
                >Login</Button
              >
            </Link>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer  -->
    <footer class="w-full py-6 bg-background border-t">
      <div class="container mx-auto px-4 md:px-6">
        <div
          class="flex flex-col items-center justify-center space-y-4 text-center"
        >
          <div class="flex items-center space-x-2">
            <Server class="h-6 w-6" />
            <span class="text-lg font-bold">JCC Framework</span>
          </div>
          <p class="text-sm text-muted-foreground">
            © {{ new Date().getFullYear() }} Framework. All rights reserved.
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { Link, Head } from "@inertiajs/vue3";
import Header from "@/Components/Header.vue";
import { Button } from "@/Components/ui/button";
import {
  ServerIcon,
  LockClosedIcon,
  CircleStackIcon,
  CodeBracketIcon,
  ArrowRightIcon,
} from "@heroicons/vue/24/outline";
</script>
