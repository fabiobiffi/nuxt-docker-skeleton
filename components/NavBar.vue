<template>
  <nav class="">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="/" class="text-white font-bold text-lg">Nuxt Application</a>
        </div>
        <!-- Mobile Menu Button -->
        <div class="-mr-2 flex md:hidden">
          <button
            @click="toggleMenu"
            type="button"
            class="bg-gray-800 inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
            aria-controls="mobile-menu"
            aria-expanded="false"
          >
            <span class="sr-only">Open main menu</span>
            <svg
              v-if="!isOpen"
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16m-7 6h7"
              />
            </svg>
            <svg
              v-else
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
        <!-- Menu and User Button -->
        <div class="hidden md:flex md:items-center md:space-x-4">
          <a
            href="#"
            class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
            >Page 1</a
          >
          <a
            href="#"
            class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
            >Page 2</a
          >
          <a
            href="#"
            class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
            >Page 3</a
          >

          <!-- Login Button -->
          <button
            class="bg-yellow-500 hover:bg-yellow-600 text-gray-900 px-3 py-2 rounded-md text-sm font-medium"
            @click="login"
          >
            Login
          </button>

          <!-- User Profile Icon -->
          <div class="relative">
            <button
              @click="toggleProfileMenu"
              class="text-gray-300 hover:text-white focus:outline-none"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M5.121 17.804A11.964 11.964 0 0112 15c3.218 0 6.154 1.263 8.121 3.804M12 11a4 4 0 100-8 4 4 0 000 8z"
                ></path>
              </svg>
            </button>
            <!-- Profile Popup -->
            <div
              v-if="isProfileMenuOpen"
              class="absolute right-0 mt-2 w-48 bg-white rounded-md shadow-lg py-2 z-20"
            >
              <a
                href="#"
                class="block px-4 py-2 text-gray-800 hover:bg-gray-200"
                >My Profile</a
              >
              <a
                href="#"
                class="block px-4 py-2 text-gray-800 hover:bg-gray-200"
                >Logout</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Mobile Menu -->
    <div v-if="isOpen" class="md:hidden" id="mobile-menu">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <a
          href="#"
          class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Home</a
        >
        <a
          href="#"
          class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >About</a
        >
        <a
          href="#"
          class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Services</a
        >
        <a
          href="#"
          class="text-gray-300 hover:bg-gray-700 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
          >Contact</a
        >
        <button
          class="bg-yellow-500 hover:bg-yellow-600 text-gray-900 block w-full text-left px-3 py-2 rounded-md text-base font-medium"
        >
          Login
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue";

const isOpen = ref(false);
const isProfileMenuOpen = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};

const toggleProfileMenu = () => {
  isProfileMenuOpen.value = !isProfileMenuOpen.value;
};

const login = () => {
  alert("Login not implemented");
};
</script>

<style scoped lang="scss">
nav {
    background-color: #222222;
}
</style>
