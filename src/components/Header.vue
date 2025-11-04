<template>
  <header class="fixed top-0 left-0 right-0 z-50 transition-all duration-500"
    :class="scrolled ? 'bg-white/10 dark:bg-gray-900/90 backdrop-blur-xl shadow-2xl shadow-primary-500/10 dark:shadow-primary-900/20 border-b border-white/20 dark:border-gray-800' : 'bg-transparent backdrop-blur-md'">
    <nav class="container mx-auto px-4 py-5">
      <div class="flex items-center justify-between">
        <a href="/" class="flex items-center space-x-2 group">
          <div
            class="w-10 h-10 bg-gradient-to-br from-primary-600 to-primary-800 rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300 shadow-lg shadow-primary-500/50">
            <Code2 :size="24" class="text-white" />
          </div>
          <span
            class="text-3xl font-bold bg-gradient-to-r from-primary-600 to-primary-800 bg-clip-text text-transparent">
            Dicka
            <span class="text-sm text-black">Tech</span>
          </span>
        </a>

        <!-- Desktop Menu -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="/"
            class="text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium relative group">
            Home
            <span
              class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 dark:bg-primary-400 transition-all group-hover:w-full"></span>
          </a>
          <a href="/#services"
            class="text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium relative group">
            Layanan
            <span
              class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 dark:bg-primary-400 transition-all group-hover:w-full"></span>
          </a>
          <a href="/#portfolio"
            class="text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium relative group">
            Portfolio
            <span
              class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 dark:bg-primary-400 transition-all group-hover:w-full"></span>
          </a>
          <a href="/blog" class="text-gray-700 hover:text-primary-600 transition-colors font-medium relative group">
            Blog
            <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 transition-all group-hover:w-full"></span>
          </a>

          <a href="#contact"
            class="bg-gradient-to-r from-primary-600 via-primary-700 to-primary-800 text-white px-6 py-2.5 rounded-xl hover:shadow-lg hover:shadow-primary-500/50 transition-all font-medium transform hover:scale-105 flex items-center space-x-2">
            <MessageCircle :size="18" />
            <span>Hubungi Kami</span>
          </a>

          <!-- Theme Toggle -->
          <!-- <button @click="toggleTheme"
            class="p-2 rounded-lg bg-gray-100 hover:bg-gray-200 dark:bg-gray-800 dark:hover:bg-gray-700 transition-colors"
            aria-label="Toggle theme">
            <Sun v-if="isDark" :size="20" class="text-gray-700 dark:text-gray-300" />
            <Moon v-else :size="20" class="text-gray-700 dark:text-gray-300" />
          </button> -->
        </div>

        <!-- Mobile Menu Button -->
        <button @click="mobileMenuOpen = !mobileMenuOpen"
          class="md:hidden text-gray-700 dark:text-gray-300 focus:outline-none hover:text-primary-600 dark:hover:text-primary-400 transition-colors"
          aria-label="Toggle menu">
          <Menu v-if="!mobileMenuOpen" :size="24" />
          <X v-else :size="24" />
        </button>
      </div>

      <!-- Mobile Menu -->
      <div v-if="mobileMenuOpen" class="md:hidden mt-4 pb-4 space-y-4 animate-slide-down">
        <a href="/"
          class="block text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium py-2">Home</a>
        <a href="/#services"
          class="block text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium py-2">Layanan</a>
        <a href="/#portfolio"
          class="block text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium py-2">Portfolio</a>
        <a href="/blog"
          class="block text-gray-700 dark:text-gray-300 hover:text-primary-600 dark:hover:text-primary-400 transition-colors font-medium py-2">Blog</a>

        <!-- Theme Toggle Mobile -->
        <!-- <button @click="toggleTheme"
          class="w-full flex items-center justify-between p-3 rounded-lg bg-gray-100 dark:bg-gray-800 hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors">
          <span class="text-gray-700 dark:text-gray-300 font-medium">Theme</span>
          <div class="flex items-center space-x-2">
            <span class="text-sm text-gray-600 dark:text-gray-400">{{ isDark ? 'Dark' : 'Light' }}</span>
            <Sun v-if="isDark" :size="20" class="text-gray-700 dark:text-gray-300" />
            <Moon v-else :size="20" class="text-gray-700 dark:text-gray-300" />
          </div>
        </button> -->

        <a href="#contact"
          class="block bg-gradient-to-r from-primary-600 via-primary-700 to-primary-800 text-white px-6 py-3 rounded-xl hover:shadow-lg transition-all font-medium text-center">
          Hubungi Kami
        </a>
      </div>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import { Code2, MessageCircle, Menu, X, Sun, Moon } from 'lucide-vue-next';
import { useTheme } from '../composables/useTheme';

const scrolled = ref(false);
const mobileMenuOpen = ref(false);
const { isDark, toggleTheme } = useTheme();

const handleScroll = () => {
  scrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
@keyframes slide-down {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-slide-down {
  animation: slide-down 0.3s ease-out;
}
</style>
