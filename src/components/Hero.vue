<template>
  <section class="relative min-h-screen flex items-center justify-center overflow-hidden pt-20">
    <!-- Animated Bright Background -->
    <div
      class="absolute inset-0 bg-gradient-to-br from-blue-100 via-purple-50 to-pink-100 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900">
      <!-- Large Animated Gradient Blobs -->
      <div
        class="absolute top-0 left-0 w-[500px] h-[500px] bg-gradient-to-br from-yellow-300 to-orange-400 dark:bg-primary-600 rounded-full mix-blend-multiply dark:mix-blend-screen filter blur-3xl opacity-50 dark:opacity-10 animate-blob">
      </div>
      <div
        class="absolute top-0 right-0 w-[500px] h-[500px] bg-gradient-to-br from-pink-300 to-purple-500 dark:bg-primary-700 rounded-full mix-blend-multiply dark:mix-blend-screen filter blur-3xl opacity-50 dark:opacity-15 animate-blob animation-delay-2000">
      </div>
      <div
        class="absolute bottom-0 left-1/2 w-[500px] h-[500px] bg-gradient-to-br from-cyan-300 to-blue-500 dark:bg-accent-600 rounded-full mix-blend-multiply dark:mix-blend-screen filter blur-3xl opacity-50 dark:opacity-10 animate-blob animation-delay-4000">
      </div>
      <div
        class="absolute top-1/2 right-1/4 w-[400px] h-[400px] bg-gradient-to-br from-green-300 to-teal-400 dark:bg-primary-500 rounded-full mix-blend-multiply dark:mix-blend-screen filter blur-3xl opacity-40 dark:opacity-10 animate-blob animation-delay-1000">
      </div>

      <!-- Decorative Geometric Ornaments -->
      <div
        class="absolute top-20 left-10 w-20 h-20 border-4 border-purple-300/40 dark:border-primary-400/20 rounded-lg rotate-12 animate-float">
      </div>
      <div
        class="absolute bottom-32 right-20 w-16 h-16 border-4 border-pink-300/40 dark:border-purple-400/20 rounded-full animate-float animation-delay-2000">
      </div>
      <div
        class="absolute top-40 right-32 w-12 h-12 bg-yellow-200/30 dark:bg-primary-400/10 rounded-lg rotate-45 animate-float animation-delay-3000">
      </div>
      <div
        class="absolute bottom-20 left-32 w-24 h-24 border-4 border-blue-300/30 dark:border-pink-400/20 rounded-full animate-float animation-delay-1000">
      </div>

      <!-- Sparkle Effects -->
      <div class="absolute top-32 left-1/4">
        <div class="w-3 h-3 bg-yellow-300 dark:bg-primary-300 rounded-full animate-pulse"></div>
      </div>
      <div class="absolute top-1/3 right-1/3">
        <div class="w-4 h-4 bg-pink-300 dark:bg-purple-300 rounded-full animate-pulse animation-delay-1000"></div>
      </div>
      <div class="absolute bottom-1/3 left-1/3">
        <div class="w-3 h-3 bg-cyan-300 dark:bg-blue-300 rounded-full animate-pulse animation-delay-2000"></div>
      </div>
      <div class="absolute top-1/2 left-1/5">
        <div class="w-2 h-2 bg-purple-300 dark:bg-primary-300 rounded-full animate-pulse animation-delay-3000"></div>
      </div>

      <!-- Pattern Overlay -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0"
          style="background-image: url('data:image/svg+xml,%3Csvg width=\'60\' height=\'60\' viewBox=\'0 0 60 60\' xmlns=\'http://www.w3.org/2000/svg\'%3E%3Cg fill=\'none\' fill-rule=\'evenodd\'%3E%3Cg fill=\'%239333ea\' fill-opacity=\'1\'%3E%3Cpath d=\'M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z\'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E');">
        </div>
      </div>
    </div>

    <div class="container mx-auto px-4 relative z-10">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-16 items-center">
        <!-- Content -->
        <div class="text-center lg:text-left space-y-8" :class="{ 'animate-fade-in': isVisible }">
          <!-- Badge -->
          <div
            class="inline-flex items-center space-x-2 bg-gradient-to-r from-purple-100 to-pink-100 dark:bg-primary-900/30 border-2 border-purple-300 dark:border-primary-800 px-5 py-2.5 rounded-full shadow-lg shadow-purple-200/50 dark:shadow-none">
            <Sparkles :size="18" class="text-purple-600 dark:text-primary-400" />
            <span class="text-sm font-bold text-purple-700 dark:text-primary-300">✨ Solusi Digital Terpercaya</span>
          </div>

          <h1
            class="text-4xl md:text-5xl lg:text-6xl xl:text-7xl font-bold text-gray-900 dark:text-white leading-tight">
            Wujudkan Website
            <span
              class="block bg-gradient-to-r from-purple-600 via-pink-500 to-orange-500 dark:from-primary-400 dark:via-primary-500 dark:to-primary-700 bg-clip-text text-transparent animate-gradient">
              Impian Bisnis Anda
            </span>
          </h1>

          <p class="text-lg md:text-xl text-gray-600 dark:text-gray-300 max-w-2xl leading-relaxed">
            Kami adalah tim profesional yang siap membantu mengembangkan website berkualitas tinggi
            dengan teknologi terkini seperti React, Laravel, WordPress, dan optimasi SEO terbaik.
          </p>

          <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
            <a href="#contact"
              class="group bg-gradient-to-r from-purple-600 via-pink-500 to-orange-500 text-white px-8 py-4 rounded-xl hover:shadow-2xl hover:shadow-purple-500/50 transition-all transform hover:scale-105 font-semibold text-lg flex items-center justify-center space-x-2 shadow-lg">
              <Rocket :size="20" />
              <span>Mulai Proyek</span>
              <ArrowRight :size="20" class="group-hover:translate-x-1 transition-transform" />
            </a>
            <a href="#portfolio"
              class="group bg-white/90 dark:bg-gray-800 text-purple-600 dark:text-primary-400 px-8 py-4 rounded-xl border-2 border-purple-300 dark:border-primary-700 hover:border-purple-600 dark:hover:border-primary-500 hover:bg-purple-50 dark:hover:bg-primary-900/30 transition-all font-semibold text-lg flex items-center justify-center space-x-2 shadow-md hover:shadow-xl backdrop-blur-sm">
              <Briefcase :size="20" />
              <span>Lihat Portfolio</span>
            </a>
          </div>

          <!-- Trust Indicators -->
          <div class="flex flex-wrap gap-6 justify-center lg:justify-start items-center pt-4">
            <div class="flex items-center space-x-2">
              <div class="flex -space-x-2">
                <div
                  class="w-8 h-8 rounded-full border-2 border-white bg-gradient-to-br from-blue-400 to-blue-600 flex items-center justify-center">
                  <User :size="16" class="text-white" />
                </div>
                <div
                  class="w-8 h-8 rounded-full border-2 border-white bg-gradient-to-br from-purple-400 to-purple-600 flex items-center justify-center">
                  <User :size="16" class="text-white" />
                </div>
                <div
                  class="w-8 h-8 rounded-full border-2 border-white bg-gradient-to-br from-pink-400 to-pink-600 flex items-center justify-center">
                  <User :size="16" class="text-white" />
                </div>
              </div>
              <span class="text-sm text-gray-600 dark:text-gray-300 font-medium">120+ Klien Puas</span>
            </div>
            <div class="flex items-center space-x-1">
              <Star :size="16" class="text-yellow-400 fill-yellow-400" />
              <Star :size="16" class="text-yellow-400 fill-yellow-400" />
              <Star :size="16" class="text-yellow-400 fill-yellow-400" />
              <Star :size="16" class="text-yellow-400 fill-yellow-400" />
              <Star :size="16" class="text-yellow-400 fill-yellow-400" />
              <span class="text-sm text-gray-600 dark:text-gray-300 font-medium ml-2">5.0 Rating</span>
            </div>
          </div>
        </div>

        <!-- Image Section with Modern Design -->
        <div class="relative" :class="{ 'animate-fade-in-right': isVisible }">
          <!-- Main Image -->
          <div class="relative z-10">
            <div class="relative rounded-2xl overflow-hidden shadow-2xl">
              <img src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?q=80&w=1200&auto=format&fit=crop"
                alt="Tim profesional Dicka Tech sedang berkolaborasi dalam pembuatan website dan solusi digital"
                title="Tim Web Development Dicka Tech" loading="eager" fetchpriority="high" width="1200" height="800"
                class="w-full h-auto object-cover rounded-2xl" />
              <div class="absolute inset-0 bg-gradient-to-t from-primary-900/20 to-transparent"></div>
            </div>

            <!-- Floating Cards with Bright Colors -->
            <div
              class="absolute -top-6 -left-6 bg-gradient-to-br from-green-50 to-emerald-100 dark:bg-gray-800 rounded-xl shadow-2xl dark:shadow-primary-900/20 p-4 animate-float border-2 border-green-200 dark:border-gray-700">
              <div class="flex items-center space-x-3">
                <div
                  class="w-12 h-12 bg-gradient-to-br from-green-400 to-emerald-500 dark:bg-green-900/30 rounded-lg flex items-center justify-center shadow-lg">
                  <CheckCircle2 :size="24" class="text-white dark:text-green-400" />
                </div>
                <div>
                  <p
                    class="text-2xl font-bold bg-gradient-to-r from-green-600 to-emerald-600 bg-clip-text text-transparent dark:text-white">
                    150+</p>
                  <p class="text-sm text-green-700 dark:text-gray-400 font-medium">Projects Done</p>
                </div>
              </div>
            </div>

            <div
              class="absolute -bottom-6 -right-6 bg-gradient-to-br from-purple-50 to-pink-100 dark:bg-gray-800 rounded-xl shadow-2xl dark:shadow-primary-900/20 p-4 animate-float animation-delay-2000 border-2 border-purple-200 dark:border-gray-700">
              <div class="flex items-center space-x-3">
                <div
                  class="w-12 h-12 bg-gradient-to-br from-purple-400 to-pink-500 dark:bg-primary-900/30 rounded-lg flex items-center justify-center shadow-lg">
                  <Users :size="24" class="text-white dark:text-primary-400" />
                </div>
                <div>
                  <p
                    class="text-2xl font-bold bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent dark:text-white">
                    98%</p>
                  <p class="text-sm text-purple-700 dark:text-gray-400 font-medium">Satisfaction</p>
                </div>
              </div>
            </div>

            <div
              class="absolute top-1/2 -right-4 bg-gradient-to-br from-yellow-50 to-orange-100 dark:bg-gray-800 rounded-xl shadow-2xl dark:shadow-primary-900/20 p-3 animate-float animation-delay-1000 border-2 border-yellow-200 dark:border-gray-700">
              <div class="flex items-center space-x-2">
                <Zap :size="20" class="text-orange-500 dark:text-yellow-400" />
                <span class="text-sm font-bold text-orange-600 dark:text-white">Fast Delivery</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce z-10">
      <ChevronDown :size="32" class="text-primary-600" />
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import {
  Sparkles,
  Rocket,
  ArrowRight,
  Briefcase,
  Star,
  CheckCircle2,
  Users,
  Zap,
  ChevronDown,
  User
} from 'lucide-vue-next';

const isVisible = ref(false);

onMounted(() => {
  setTimeout(() => {
    isVisible.value = true;
  }, 100);
});
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fade-in-right {
  from {
    opacity: 0;
    transform: translateX(20px);
  }

  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes blob {

  0%,
  100% {
    transform: translate(0, 0) scale(1);
  }

  33% {
    transform: translate(30px, -50px) scale(1.1);
  }

  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
}

@keyframes float {

  0%,
  100% {
    transform: translateY(0px);
  }

  50% {
    transform: translateY(-10px);
  }
}

@keyframes pulse {

  0%,
  100% {
    opacity: 1;
    transform: scale(1);
  }

  50% {
    opacity: 0.5;
    transform: scale(1.5);
  }
}

.animate-fade-in {
  animation: fade-in 0.8s ease-out;
}

.animate-fade-in-right {
  animation: fade-in-right 0.8s ease-out;
}

.animate-blob {
  animation: blob 7s infinite;
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}

.animate-pulse {
  animation: pulse 3s ease-in-out infinite;
}

.animation-delay-1000 {
  animation-delay: 1s;
}

.animation-delay-2000 {
  animation-delay: 2s;
}

.animation-delay-3000 {
  animation-delay: 3s;
}

.animation-delay-4000 {
  animation-delay: 4s;
}
</style>
