<template>
  <section id="portfolio"
    class="py-20 bg-gradient-to-br from-pink-50 via-purple-50 to-blue-50 dark:bg-gray-900 relative overflow-hidden">
    <!-- Decorative blobs -->
    <div class="absolute inset-0 opacity-20 dark:opacity-5 pointer-events-none">
      <div
        class="absolute top-10 left-20 w-72 h-72 bg-gradient-to-br from-pink-300 to-rose-400 rounded-full filter blur-3xl">
      </div>
      <div
        class="absolute bottom-10 right-20 w-72 h-72 bg-gradient-to-br from-blue-300 to-cyan-400 rounded-full filter blur-3xl">
      </div>
    </div>
    <div class="container mx-auto px-4 relative z-10">
      <div class="text-center mb-16">
        <div
          class="inline-flex items-center space-x-2 bg-gradient-to-r from-pink-100 to-purple-100 dark:bg-primary-900/30 border-2 border-pink-300 dark:border-primary-800 px-5 py-2.5 rounded-full shadow-lg shadow-pink-200/50 dark:shadow-none mb-4">
          <span class="text-sm font-bold text-pink-700 dark:text-primary-300">🎨 Portfolio</span>
        </div>
        <h2
          class="text-3xl md:text-4xl font-bold bg-gradient-to-r from-pink-600 via-purple-600 to-blue-600 bg-clip-text text-transparent dark:text-white mb-4">
          Portfolio Kami
        </h2>
        <p class="text-lg text-gray-700 dark:text-gray-300 max-w-2xl mx-auto font-medium">
          Lihat hasil karya terbaik kami yang telah membantu berbagai bisnis berkembang
        </p>
      </div>

      <!-- Filter Tabs -->
      <div class="flex flex-wrap justify-center gap-4 mb-12">
        <button v-for="category in categories" :key="category" @click="selectedCategory = category"
          class="px-6 py-2.5 rounded-xl font-semibold transition-all"
          :class="selectedCategory === category
            ? 'bg-gradient-to-r from-pink-500 to-purple-600 text-white shadow-xl shadow-pink-500/30'
            : 'bg-white dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-gradient-to-r hover:from-pink-50 hover:to-purple-50 dark:hover:bg-gray-700 border-2 border-pink-200/50 dark:border-gray-700'">
          {{ category }}
        </button>
      </div>

      <!-- Portfolio Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(project, index) in filteredProjects" :key="index"
          class="group relative overflow-hidden rounded-xl shadow-lg hover:shadow-2xl dark:shadow-primary-900/20 transition-all duration-300 transform hover:-translate-y-2 cursor-pointer bg-gray-100 dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
          <div class="aspect-video relative overflow-hidden">
            <!-- Project Image -->
            <img :src="project.image" :alt="project.title"
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
              loading="lazy" />

            <!-- Overlay -->
            <div
              class="absolute inset-0 bg-gradient-to-t from-gray-900 via-gray-900/40 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
              <div class="absolute bottom-0 left-0 right-0 p-6">
                <div class="flex items-center gap-4">
                  <a href="#"
                    class="bg-white dark:bg-gray-800 text-primary-600 dark:text-primary-400 px-4 py-2 rounded-lg font-medium hover:bg-primary-50 dark:hover:bg-primary-900/30 transition-colors">
                    View Project
                  </a>
                  <a href="#"
                    class="bg-primary-600 dark:bg-primary-700 text-white p-2 rounded-lg hover:bg-primary-700 dark:hover:bg-primary-800 transition-colors">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                        d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
                    </svg>
                  </a>
                </div>
              </div>
            </div>
          </div>

          <div class="p-6">
            <div class="flex items-center gap-2 mb-2">
              <span
                class="text-xs font-semibold text-primary-600 dark:text-primary-400 bg-primary-50 dark:bg-primary-900/30 px-3 py-1 rounded-full">
                {{ project.category }}
              </span>
            </div>
            <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-2">{{ project.title }}</h3>
            <p class="text-gray-600 dark:text-gray-300 text-sm mb-4">{{ project.description }}</p>
            <div class="flex flex-wrap gap-2">
              <span v-for="tech in project.tech" :key="tech"
                class="text-xs text-gray-600 dark:text-gray-400 bg-gray-100 dark:bg-gray-700 px-2 py-1 rounded">
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const selectedCategory = ref('Semua');
const categories = ['Semua', 'Web Development', 'E-Commerce', 'Corporate', 'Landing Page'];

interface Project {
  title: string;
  category: string;
  description: string;
  tech: string[];
  image: string;
}

const projects: Project[] = [
  {
    title: 'E-Commerce Fashion Store',
    category: 'E-Commerce',
    description: 'Platform e-commerce dengan fitur pembayaran lengkap dan manajemen inventory',
    tech: ['React', 'Node.js', 'MongoDB'],
    image: 'https://images.unsplash.com/photo-1441984904996-e0b6ba687e04?w=800&q=80'
  },
  {
    title: 'Corporate Banking Website',
    category: 'Corporate',
    description: 'Website corporate untuk institusi perbankan dengan dashboard admin',
    tech: ['Laravel', 'MySQL', 'Vue.js'],
    image: 'https://images.unsplash.com/photo-1551434678-e076c223a692?w=800&q=80'
  },
  {
    title: 'SaaS Landing Page',
    category: 'Landing Page',
    description: 'Landing page modern untuk produk SaaS dengan konversi tinggi',
    tech: ['Next.js', 'Tailwind', 'TypeScript'],
    image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=800&q=80'
  },
  {
    title: 'Restaurant Booking System',
    category: 'Web Development',
    description: 'Sistem reservasi online untuk restoran dengan notifikasi real-time',
    tech: ['React', 'Firebase', 'Stripe'],
    image: 'https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=800&q=80'
  },
  {
    title: 'Property Marketplace',
    category: 'E-Commerce',
    description: 'Platform marketplace properti dengan fitur pencarian advanced',
    tech: ['Laravel', 'Vue.js', 'PostgreSQL'],
    image: 'https://images.unsplash.com/photo-1560518883-ce09059eeffa?w=800&q=80'
  },
  {
    title: 'Healthcare Portal',
    category: 'Corporate',
    description: 'Portal kesehatan untuk booking dokter dan telemedicine',
    tech: ['React', 'Node.js', 'WebRTC'],
    image: 'https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?w=800&q=80'
  }
];

const filteredProjects = computed(() => {
  if (selectedCategory.value === 'Semua') {
    return projects;
  }
  return projects.filter(project => project.category === selectedCategory.value);
});
</script>
