<template>
  <section id="services" class="py-20 bg-gradient-to-br from-blue-50 via-purple-50 to-pink-50 dark:bg-gray-800 relative overflow-hidden">
    <!-- Decorative blobs -->
    <div class="absolute inset-0 opacity-20 dark:opacity-5 pointer-events-none">
      <div class="absolute top-20 left-10 w-72 h-72 bg-gradient-to-br from-yellow-300 to-orange-400 rounded-full filter blur-3xl"></div>
      <div class="absolute bottom-20 right-10 w-72 h-72 bg-gradient-to-br from-pink-300 to-purple-400 rounded-full filter blur-3xl"></div>
    </div>
    <div class="container mx-auto px-4 relative z-10">
      <div class="text-center mb-16">
        <div class="inline-flex items-center space-x-2 bg-gradient-to-r from-blue-100 to-purple-100 dark:bg-primary-900/30 border-2 border-blue-300 dark:border-primary-800 px-5 py-2.5 rounded-full shadow-lg shadow-blue-200/50 dark:shadow-none mb-4">
          <span class="text-sm font-bold text-blue-700 dark:text-primary-300">💼 Our Services</span>
        </div>
        <h2 class="text-3xl md:text-4xl font-bold bg-gradient-to-r from-blue-600 via-purple-600 to-pink-600 bg-clip-text text-transparent dark:text-white mb-4">
          Layanan Kami
        </h2>
        <p class="text-lg text-gray-700 dark:text-gray-300 max-w-2xl mx-auto font-medium">
          Solusi digital lengkap untuk mengembangkan bisnis Anda dengan teknologi terkini
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(service, index) in services" :key="index"
          class="bg-gradient-to-br from-white to-blue-50/30 dark:bg-gray-900 rounded-2xl p-8 shadow-xl hover:shadow-2xl dark:shadow-primary-900/20 transition-all duration-300 transform hover:-translate-y-2 cursor-pointer group border-2 border-blue-200/50 dark:border-gray-800 hover:border-purple-300 dark:hover:border-primary-600">
          <div
            :class="[
              'w-16 h-16 rounded-xl flex items-center justify-center mb-6 transition-all duration-300 shadow-lg',
              'group-hover:scale-110',
              index % 6 === 0 ? 'bg-gradient-to-br from-blue-400 to-cyan-500 shadow-blue-500/40' : '',
              index % 6 === 1 ? 'bg-gradient-to-br from-purple-400 to-pink-500 shadow-purple-500/40' : '',
              index % 6 === 2 ? 'bg-gradient-to-br from-orange-400 to-yellow-500 shadow-orange-500/40' : '',
              index % 6 === 3 ? 'bg-gradient-to-br from-green-400 to-emerald-500 shadow-green-500/40' : '',
              index % 6 === 4 ? 'bg-gradient-to-br from-pink-400 to-rose-500 shadow-pink-500/40' : '',
              index % 6 === 5 ? 'bg-gradient-to-br from-cyan-400 to-blue-500 shadow-cyan-500/40' : ''
            ]">
            <component :is="service.icon" class="w-8 h-8 text-white transition-transform" />
          </div>
          <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-3">{{ service.title }}</h3>
          <p class="text-gray-600 dark:text-gray-300 mb-4">{{ service.description }}</p>
          <ul class="space-y-2">
            <li v-for="(feature, idx) in service.features" :key="idx" class="flex items-start text-sm text-gray-600 dark:text-gray-400">
              <CheckCircle2 :size="18" class="text-primary-600 dark:text-primary-400 mr-2 flex-shrink-0 mt-0.5" />
              {{ feature }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Code2, Search, FileText, Zap, Terminal, Smartphone, CheckCircle2 } from 'lucide-vue-next';
import { markRaw } from 'vue';

const services = [
  {
    icon: markRaw(Code2),
    title: 'Website Development',
    description: 'Pembuatan website custom dengan desain modern dan performa optimal',
    features: [
      'Responsive Design',
      'Fast Loading Speed',
      'SEO Friendly',
      'Modern UI/UX'
    ],
    color: 'blue'
  },
  {
    icon: markRaw(Search),
    title: 'SEO Optimization',
    description: 'Tingkatkan ranking website Anda di mesin pencari Google',
    features: [
      'On-Page SEO',
      'Technical SEO',
      'Keyword Research',
      'Content Strategy'
    ],
    color: 'green'
  },
  {
    icon: markRaw(FileText),
    title: 'WordPress Development',
    description: 'Solusi WordPress lengkap untuk blog dan corporate website',
    features: [
      'Custom Theme',
      'Plugin Development',
      'E-Commerce Setup',
      'Maintenance & Support'
    ],
    color: 'purple'
  },
  {
    icon: markRaw(Zap),
    title: 'React Development',
    description: 'Aplikasi web modern dengan React.js dan Next.js',
    features: [
      'Single Page Application',
      'Server Side Rendering',
      'Progressive Web App',
      'Real-time Features'
    ],
    color: 'cyan'
  },
  {
    icon: markRaw(Terminal),
    title: 'Laravel Development',
    description: 'Backend robust dengan framework Laravel PHP',
    features: [
      'RESTful API',
      'Admin Dashboard',
      'Database Design',
      'Security Implementation'
    ],
    color: 'red'
  },
  {
    icon: markRaw(Smartphone),
    title: 'Mobile App Development',
    description: 'Aplikasi mobile untuk iOS dan Android',
    features: [
      'Cross-Platform',
      'Native Performance',
      'Push Notifications',
      'App Store Deployment'
    ],
    color: 'orange'
  }
];
</script>
