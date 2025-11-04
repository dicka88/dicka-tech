<template>
  <section class="py-16 bg-gradient-to-br from-purple-50 via-pink-50 to-orange-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 relative overflow-hidden">
    <!-- Background decoration -->
    <div class="absolute inset-0 opacity-20 dark:opacity-5">
      <div class="absolute top-0 left-0 w-96 h-96 bg-gradient-to-br from-purple-300 to-pink-400 dark:bg-primary-700 rounded-full filter blur-3xl"></div>
      <div class="absolute bottom-0 right-0 w-96 h-96 bg-gradient-to-br from-orange-300 to-yellow-400 dark:bg-accent-600 rounded-full filter blur-3xl"></div>
      <div class="absolute top-1/2 left-1/2 w-64 h-64 bg-gradient-to-br from-cyan-300 to-blue-400 dark:bg-primary-500 rounded-full filter blur-3xl"></div>
    </div>

    <div class="container mx-auto px-4 relative z-10">
      <div class="grid grid-cols-2 md:grid-cols-4 gap-6 md:gap-8">
        <div v-for="(stat, index) in stats" :key="index" class="relative group"
          :class="{ 'animate-count-up': isVisible }" :style="{ animationDelay: `${index * 100}ms` }">
          <div
            class="bg-gradient-to-br from-white to-purple-50/50 dark:bg-gray-800 rounded-2xl p-6 md:p-8 shadow-xl hover:shadow-2xl dark:shadow-primary-900/20 transition-all duration-300 transform hover:-translate-y-2 border-2 border-purple-200/50 dark:border-gray-700">
            <!-- Icon -->
            <div class="flex justify-center mb-4">
              <div
                :class="[
                  'w-14 h-14 rounded-xl flex items-center justify-center transform group-hover:scale-110 transition-transform duration-300 shadow-lg',
                  index === 0 ? 'bg-gradient-to-br from-green-400 to-emerald-500 shadow-green-500/40' : '',
                  index === 1 ? 'bg-gradient-to-br from-purple-400 to-pink-500 shadow-purple-500/40' : '',
                  index === 2 ? 'bg-gradient-to-br from-orange-400 to-yellow-500 shadow-orange-500/40' : '',
                  index === 3 ? 'bg-gradient-to-br from-cyan-400 to-blue-500 shadow-cyan-500/40' : ''
                ]">
                <component :is="stat.icon" :size="28" class="text-white" />
              </div>
            </div>

            <!-- Number -->
            <div
              :class="[
                'text-3xl md:text-4xl lg:text-5xl font-bold bg-clip-text text-transparent mb-2',
                index === 0 ? 'bg-gradient-to-r from-green-600 to-emerald-600' : '',
                index === 1 ? 'bg-gradient-to-r from-purple-600 to-pink-600' : '',
                index === 2 ? 'bg-gradient-to-r from-orange-600 to-yellow-600' : '',
                index === 3 ? 'bg-gradient-to-r from-cyan-600 to-blue-600' : ''
              ]">
              {{ stat.value }}{{ stat.suffix }}
            </div>

            <!-- Label -->
            <div class="text-gray-700 dark:text-gray-300 font-semibold text-sm md:text-base">{{ stat.label }}</div>

            <!-- Progress bar -->
            <div class="mt-4 h-1.5 bg-gradient-to-r from-gray-100 to-gray-200 dark:bg-gray-700 rounded-full overflow-hidden">
              <div
                :class="[
                  'h-full rounded-full transition-all duration-1000',
                  { 'w-full': isVisible, 'w-0': !isVisible },
                  index === 0 ? 'bg-gradient-to-r from-green-400 to-emerald-500' : '',
                  index === 1 ? 'bg-gradient-to-r from-purple-400 to-pink-500' : '',
                  index === 2 ? 'bg-gradient-to-r from-orange-400 to-yellow-500' : '',
                  index === 3 ? 'bg-gradient-to-r from-cyan-400 to-blue-500' : ''
                ]" :style="{ transitionDelay: `${index * 100}ms` }">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { CheckCircle2, Users, Calendar, TrendingUp } from 'lucide-vue-next';
import { markRaw } from 'vue';

const isVisible = ref(false);

const stats = [
  {
    value: '150',
    suffix: '+',
    label: 'Proyek Selesai',
    icon: markRaw(CheckCircle2)
  },
  {
    value: '120',
    suffix: '+',
    label: 'Klien Puas',
    icon: markRaw(Users)
  },
  {
    value: '5',
    suffix: '+',
    label: 'Tahun Pengalaman',
    icon: markRaw(Calendar)
  },
  {
    value: '98',
    suffix: '%',
    label: 'Tingkat Kepuasan',
    icon: markRaw(TrendingUp)
  },
];

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        isVisible.value = true;
      }
    });
  });

  const element = document.querySelector('.py-16');
  if (element) observer.observe(element);
});
</script>

<style scoped>
@keyframes count-up {
  from {
    opacity: 0;
    transform: translateY(20px) scale(0.9);
  }

  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.animate-count-up {
  animation: count-up 0.6s ease-out;
}
</style>
