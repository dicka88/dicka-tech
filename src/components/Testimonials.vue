<template>
  <section
    class="py-20 bg-gradient-to-br from-green-50 via-emerald-50 to-teal-50 dark:bg-gray-800 relative overflow-hidden">
    <!-- Decorative blobs -->
    <div class="absolute inset-0 opacity-20 dark:opacity-5 pointer-events-none">
      <div
        class="absolute top-20 left-10 w-72 h-72 bg-gradient-to-br from-green-300 to-emerald-400 rounded-full filter blur-3xl">
      </div>
      <div
        class="absolute bottom-20 right-10 w-72 h-72 bg-gradient-to-br from-teal-300 to-cyan-400 rounded-full filter blur-3xl">
      </div>
    </div>
    <div class="container mx-auto px-4 relative z-10">
      <div class="text-center mb-16">
        <div
          class="inline-flex items-center space-x-2 bg-gradient-to-r from-green-100 to-emerald-100 dark:bg-primary-900/30 border-2 border-green-300 dark:border-primary-800 px-5 py-2.5 rounded-full shadow-lg shadow-green-200/50 dark:shadow-none mb-4">
          <span class="text-sm font-bold text-green-700 dark:text-primary-300">⭐ Testimonials</span>
        </div>
        <h2
          class="text-3xl md:text-4xl font-bold bg-gradient-to-r from-green-600 via-emerald-600 to-teal-600 bg-clip-text text-transparent dark:text-white mb-4">
          Kata Mereka
        </h2>
        <p class="text-lg text-gray-700 dark:text-gray-300 max-w-2xl mx-auto font-medium">
          Testimoni dari klien yang telah mempercayai kami
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(testimonial, index) in testimonials" :key="index"
          class="bg-gradient-to-br from-white to-green-50/30 dark:bg-gray-900 rounded-2xl p-8 shadow-xl hover:shadow-2xl dark:shadow-primary-900/20 transition-all duration-300 transform hover:-translate-y-1 border-2 border-green-200/50 dark:border-gray-800">
          <!-- Stars -->
          <div class="flex gap-1 mb-4">
            <svg v-for="i in 5" :key="i" class="w-5 h-5 text-yellow-400" fill="currentColor" viewBox="0 0 20 20">
              <path
                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
            </svg>
          </div>

          <!-- Quote -->
          <p class="text-gray-700 mb-6 italic">
            "{{ testimonial.quote }}"
          </p>

          <!-- Author -->
          <div class="flex items-center gap-4">
            <div
              class="w-12 h-12 rounded-full bg-gradient-to-br from-primary-400 to-blue-500 flex items-center justify-center text-white font-bold text-lg">
              {{ testimonial.name.charAt(0) }}
            </div>
            <div>
              <div class="font-bold text-gray-900 dark:text-white">{{ testimonial.name }}</div>
              <div class="text-sm text-gray-600 dark:text-gray-400">{{ testimonial.position }}</div>
              <div class="text-sm text-gray-500 dark:text-gray-500">{{ testimonial.company }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const testimonials = [
  {
    name: 'Budi Santoso',
    position: 'CEO',
    company: 'TechStart Indonesia',
    quote: 'Dicka Tech sangat profesional dan responsif. Website kami sekarang jauh lebih cepat dan menarik. Traffic meningkat 200% dalam 3 bulan!'
  },
  {
    name: 'Siti Nurhaliza',
    position: 'Marketing Manager',
    company: 'Fashion Retail Co',
    quote: 'Tim yang sangat kompeten! Mereka berhasil membuat e-commerce yang user-friendly dan meningkatkan konversi penjualan kami secara signifikan.'
  },
  {
    name: 'Ahmad Fauzi',
    position: 'Founder',
    company: 'EduTech Platform',
    quote: 'Pelayanan luar biasa dari awal hingga akhir. Website learning platform kami sekarang bisa handle ribuan user concurrent tanpa masalah.'
  },
  {
    name: 'Diana Putri',
    position: 'Owner',
    company: 'Kuliner Nusantara',
    quote: 'Desain website yang modern dan sistem booking yang mudah digunakan. Pelanggan kami sangat puas dengan kemudahan reservasi online.'
  },
  {
    name: 'Rizky Pratama',
    position: 'CTO',
    company: 'FinTech Solutions',
    quote: 'Implementasi Laravel API yang robust dan secure. Dokumentasi lengkap dan support yang responsif. Highly recommended!'
  },
  {
    name: 'Linda Wijaya',
    position: 'Marketing Director',
    company: 'Property Group',
    quote: 'SEO optimization mereka membuat website kami ranking #1 di Google untuk keywords utama. ROI yang sangat memuaskan!'
  }
];
</script>
