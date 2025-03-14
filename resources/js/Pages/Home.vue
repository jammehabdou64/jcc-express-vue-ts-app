<template>
  <Head>
    <title>Welcome</title>
    <meta name="description" content="Your page description" />
  </Head>
  <div class="flex flex-col min-h-screen">
    <div class="flex">
      <!-- Sidebar -->
      <aside class="hidden md:flex w-64 flex-col h-screen bg-muted border-r">
        <div class="p-4 border-b">
          <h2 class="text-xl font-bold">Dashboard</h2>
        </div>
        <nav class="flex-1 p-4 space-y-1">
          <Button
            v-for="item in sidebarItems"
            :key="item.name"
            variant="ghost"
            class="w-full justify-start"
          >
            <component :is="item.icon" class="mr-2 h-4 w-4" />
            {{ item.name }}
          </Button>
        </nav>
        <div class="p-4 border-t">
          <Link href="handleLogout"> Logout </Link>
        </div>
      </aside>

      <!-- Main content -->
      <main class="flex-1 p-6 overflow-auto">
        <div class="flex items-center justify-between mb-6">
          <h1 class="text-2xl font-bold">Welcome to Your Dashboard</h1>
          <Link href="/logout"> Logout </Link>
        </div>

        <!-- Stats cards -->
        <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-4 mb-6">
          <Card v-for="stat in stats" :key="stat.title">
            <CardHeader class="flex flex-row items-center justify-between pb-2">
              <CardTitle class="text-sm font-medium">{{
                stat.title
              }}</CardTitle>
              <component
                :is="stat.icon"
                class="h-4 w-4 text-muted-foreground"
              />
            </CardHeader>
            <CardContent>
              <div class="text-2xl font-bold">{{ stat.value }}</div>
              <p class="text-xs text-muted-foreground">{{ stat.change }}</p>
            </CardContent>
          </Card>
        </div>

        <!-- Recent activity -->
        <Card class="mb-6">
          <CardHeader>
            <CardTitle>Recent Activity</CardTitle>
            <CardDescription
              >Your recent actions and system events</CardDescription
            >
          </CardHeader>
          <CardContent>
            <div class="space-y-4">
              <div
                v-for="(activity, i) in activities"
                :key="i"
                class="flex items-center gap-4 rounded-lg border p-3"
              >
                <div class="rounded-full bg-primary/10 p-2">
                  <ServerIcon class="h-4 w-4 text-primary" />
                </div>
                <div class="flex-1 space-y-1">
                  <p class="text-sm font-medium">{{ activity.title }}</p>
                  <p class="text-xs text-muted-foreground">
                    {{ activity.description }}
                  </p>
                </div>
                <div class="text-xs text-muted-foreground">
                  {{ activity.time }}
                </div>
              </div>
            </div>
          </CardContent>
        </Card>

        <!-- Documentation -->
        <Card>
          <CardHeader>
            <CardTitle>Quick Documentation</CardTitle>
            <CardDescription
              >Get started with your Express Framework</CardDescription
            >
          </CardHeader>
          <CardContent>
            <div class="space-y-4">
              <div
                v-for="doc in documentation"
                :key="doc.title"
                class="rounded-lg border p-3"
              >
                <h3 class="font-medium">{{ doc.title }}</h3>
                <pre class="mt-2 rounded-md bg-muted p-2 text-sm">
                  <code>{{ doc.code }}</code>
                </pre>
              </div>
            </div>
          </CardContent>
        </Card>
      </main>
    </div>
  </div>
</template>
<script setup lang="ts">
import { usePage, Head } from "@inertiajs/vue3";
const auth = usePage().props?.auth;

const sidebarItems = [
  { name: "Overview", icon: ServerIcon },
  { name: "Documentation", icon: FileTextIcon },
  { name: "Database", icon: DatabaseIcon },
  { name: "Users", icon: UsersIcon },
  { name: "Settings", icon: SettingsIcon },
];

const stats = [
  {
    title: "Total Users",
    value: "1,234",
    change: "+12% from last month",
    icon: UsersIcon,
  },
  {
    title: "API Requests",
    value: "45.2k",
    change: "+8% from last month",
    icon: ServerIcon,
  },
  {
    title: "Response Time",
    value: "42ms",
    change: "-3ms from last month",
    icon: ClockIcon,
  },
  {
    title: "Active Projects",
    value: "12",
    change: "+2 from last month",
    icon: BarChartIcon,
  },
];

const activities = [
  {
    title: "API Endpoint Created",
    description: "You created a new API endpoint: /api/users/1",
    time: "1h ago",
  },
  {
    title: "API Endpoint Created",
    description: "You created a new API endpoint: /api/users/2",
    time: "2h ago",
  },
  {
    title: "API Endpoint Created",
    description: "You created a new API endpoint: /api/users/3",
    time: "3h ago",
  },
  {
    title: "API Endpoint Created",
    description: "You created a new API endpoint: /api/users/4",
    time: "4h ago",
  },
  {
    title: "API Endpoint Created",
    description: "You created a new API endpoint: /api/users/5",
    time: "5h ago",
  },
];

const documentation = [
  {
    title: "Creating a new route",
    code: "app.route('/users').get(getUsers).post(createUser)",
  },
  { title: "Adding middleware", code: "app.use(authMiddleware)" },
  { title: "Database connection", code: "app.connectDB(config)" },
];
</script>
