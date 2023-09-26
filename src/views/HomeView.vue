<template>
  <div
    class="container mx-auto min-h-screen flex flex-col items-center justify-center"
  >
    <h1 class="text-3xl text-slate-600 font-bold mb-5">This is Home Page</h1>
    <div class="flex items-center space-x-5">
      <router-link
        :to="{ name: 'register' }"
        class="bg-blue-600 text-white text-xs rounded-sm px-3 py-2 font-semibold hover:bg-blue-700"
      >
        Register
      </router-link>
      <router-link
        :to="{ name: 'login' }"
        class="bg-gray-100 text-slate-700 text-xs rounded-sm px-3 py-2 font-semibold hover:bg-gray-200 border border-gray-300"
      >
        Login
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: {},
};
</script>
