<script setup>
import logo from '@/assets/img/logo.png'
import { RouterLink, useRoute} from 'vue-router';

const isActiveLink = (routePath) => {
  const route = useRoute();
  return route.path === routePath;
}

</script>
<template>
<nav class="bg-green-700 border-b border-green-500">
      <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
        <div class="flex h-20 items-center justify-between">
          <div
            class="flex flex-1 items-center justify-center md:items-stretch md:justify-start"
          >
            <!-- Logo -->
            <router-link class="flex flex-shrink-0 items-center mr-4" to="/">
              <img class="h-10 w-auto" :src="logo" alt="Vue Jobs" />
              <span class="hidden md:block text-white text-6xl font-bold ml-2"
                >Vue Jobs</span
              >
            </router-link>
            <div class="md:ml-auto">
              <div class="flex space-x-2">
                <router-link
                  to="/"
                  :class="[isActiveLink('/') ? 'bg-green-900' : 'hover:bg-gray-900 hover:text-white' ,'text-white', 'px-3', 'py-2','rounded-md']"
                  >Home</router-link
                >
                <router-link
                  to="/jobs"
                  :class="[isActiveLink('/jobs') ? 'bg-green-900' : 'hover:bg-gray-900 hover:text-white' ,'text-white', 'px-3', 'py-2','rounded-md']"
                  >Jobs</router-link
                >
                <router-link
                  to="/jobs/add"
                  :class="[isActiveLink('/jobs/add') ? 'bg-green-900' : 'hover:bg-gray-900 hover:text-white' ,'text-white', 'px-3', 'py-2','rounded-md']"
                  >Add Job</router-link
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>