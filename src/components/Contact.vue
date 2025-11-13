<!-- eslint-disable vue/no-parsing-error -->
<template>
  <section id="contact"
    class="py-20 bg-gradient-to-br from-purple-50 via-pink-50 to-orange-50 dark:bg-gray-900 relative overflow-hidden">
    <!-- Decorative blobs -->
    <div class="absolute inset-0 opacity-20 dark:opacity-5 pointer-events-none">
      <div
        class="absolute top-20 left-10 w-96 h-96 bg-gradient-to-br from-purple-300 to-pink-400 rounded-full filter blur-3xl animate-blob">
      </div>
      <div
        class="absolute bottom-20 right-10 w-96 h-96 bg-gradient-to-br from-orange-300 to-yellow-400 rounded-full filter blur-3xl animate-blob animation-delay-2000">
      </div>
      <div
        class="absolute top-1/2 left-1/2 w-80 h-80 bg-gradient-to-br from-cyan-300 to-blue-400 rounded-full filter blur-3xl animate-blob animation-delay-4000">
      </div>
    </div>

    <div class="container mx-auto px-4 relative z-10">
      <div class="text-center mb-16">
        <div
          class="inline-flex items-center space-x-2 bg-gradient-to-r from-purple-100 to-pink-100 dark:bg-primary-900/30 border-2 border-purple-300 dark:border-primary-800 px-5 py-2.5 rounded-full shadow-lg shadow-purple-200/50 dark:shadow-none mb-4">
          <span class="text-sm font-bold text-purple-700 dark:text-primary-300">💬 Let's Talk</span>
        </div>
        <h2
          class="text-3xl md:text-4xl lg:text-5xl font-bold bg-gradient-to-r from-purple-600 via-pink-500 to-orange-500 bg-clip-text text-transparent dark:text-white mb-4">
          Mulai Proyek Anda
        </h2>
        <p class="text-lg text-gray-700 dark:text-gray-300 max-w-2xl mx-auto font-medium">
          Ceritakan ide Anda kepada kami. Tim expert kami siap membantu mewujudkan impian digital Anda!
        </p>
      </div>

      <!-- Quick Contact Buttons -->
      <div class="flex flex-wrap justify-center gap-4 mb-12">
        <a href="https://wa.me/628515555555" target="_blank" rel="noopener noreferrer"
          class="group flex items-center gap-2 bg-gradient-to-r from-green-500 to-emerald-600 text-white px-6 py-3 rounded-xl font-semibold shadow-lg hover:shadow-xl hover:scale-105 transition-all">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.890-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z" />
          </svg>
          <span>WhatsApp</span>
        </a>
        <a href="mailto:dickaismaji@gmail.com"
          class="group flex items-center gap-2 bg-gradient-to-r from-blue-500 to-cyan-600 text-white px-6 py-3 rounded-xl font-semibold shadow-lg hover:shadow-xl hover:scale-105 transition-all">
          <Mail :size="20" />
          <span>Email</span>
        </a>
        <a href="tel:+628515555555"
          class="group flex items-center gap-2 bg-gradient-to-r from-purple-500 to-pink-600 text-white px-6 py-3 rounded-xl font-semibold shadow-lg hover:shadow-xl hover:scale-105 transition-all">
          <Phone :size="20" />
          <span>Telepon</span>
        </a>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-5 gap-8 max-w-7xl mx-auto">
        <!-- Contact Form -->
        <div
          class="lg:col-span-3 bg-gradient-to-br from-white to-purple-50/30 dark:bg-gray-800 rounded-2xl shadow-2xl dark:shadow-primary-900/20 p-8 md:p-10 border-2 border-purple-200/50 dark:border-gray-700">
          <div class="flex items-center gap-3 mb-6">
            <div
              class="w-12 h-12 bg-gradient-to-br from-purple-500 to-pink-600 rounded-xl flex items-center justify-center shadow-lg">
              <MessageSquare :size="24" class="text-white" />
            </div>
            <div>
              <h3
                class="text-2xl font-bold bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent dark:text-white">
                Kirim Pesan</h3>
              <p class="text-sm text-gray-600 dark:text-gray-400">Kami akan merespon dalam 24 jam</p>
            </div>
          </div>

          <form @submit.prevent="handleSubmit" class="space-y-5">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-5">
              <!-- Name Input -->
              <div class="relative">
                <label for="name" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">
                  Nama Lengkap *
                </label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
                    <User :size="18" class="text-purple-500" />
                  </div>
                  <input id="name" v-model="form.name" type="text" required
                    class="w-full pl-11 pr-4 py-3.5 border-2 border-gray-200 dark:border-gray-600 bg-white dark:bg-gray-700 text-gray-900 dark:text-white rounded-xl focus:ring-2 focus:ring-purple-500 focus:border-purple-500 dark:focus:border-purple-400 outline-none transition-all"
                    placeholder="John Doe" />
                </div>
              </div>

              <!-- Email Input -->
              <div class="relative">
                <label for="email" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">
                  Email *
                </label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
                    <Mail :size="18" class="text-pink-500" />
                  </div>
                  <input id="email" v-model="form.email" type="email" required
                    class="w-full pl-11 pr-4 py-3.5 border-2 border-gray-200 dark:border-gray-600 bg-white dark:bg-gray-700 text-gray-900 dark:text-white rounded-xl focus:ring-2 focus:ring-pink-500 focus:border-pink-500 dark:focus:border-pink-400 outline-none transition-all"
                    placeholder="john@example.com" />
                </div>
              </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-5">
              <!-- Phone Input -->
              <div class="relative">
                <label for="phone" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">
                  No. Telepon
                </label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
                    <Phone :size="18" class="text-orange-500" />
                  </div>
                  <input id="phone" v-model="form.phone" type="tel"
                    class="w-full pl-11 pr-4 py-3.5 border-2 border-gray-200 dark:border-gray-600 bg-white dark:bg-gray-700 text-gray-900 dark:text-white rounded-xl focus:ring-2 focus:ring-orange-500 focus:border-orange-500 dark:focus:border-orange-400 outline-none transition-all"
                    placeholder="+62 812 3456 7890" />
                </div>
              </div>

              <!-- Service Select -->
              <div class="relative">
                <label for="service" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">
                  Layanan *
                </label>
                <div class="relative">
                  <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
                    <Briefcase :size="18" class="text-cyan-500" />
                  </div>
                  <select id="service" v-model="form.service" required
                    class="w-full pl-11 pr-4 py-3.5 border-2 border-gray-200 dark:border-gray-600 bg-white dark:bg-gray-700 text-gray-900 dark:text-white rounded-xl focus:ring-2 focus:ring-cyan-500 focus:border-cyan-500 dark:focus:border-cyan-400 outline-none transition-all appearance-none cursor-pointer">
                    <option value="">Pilih Layanan</option>
                    <option value="web-development">🌐 Website Development</option>
                    <option value="seo">🔍 SEO Optimization</option>
                    <option value="wordpress">📝 WordPress Development</option>
                    <option value="react">⚛️ React Development</option>
                    <option value="laravel">🔴 Laravel Development</option>
                    <option value="mobile">📱 Mobile App Development</option>
                  </select>
                  <div class="absolute inset-y-0 right-0 pr-4 flex items-center pointer-events-none">
                    <ChevronDown :size="18" class="text-gray-400" />
                  </div>
                </div>
              </div>
            </div>

            <!-- Message Textarea -->
            <div class="relative">
              <label for="message" class="block text-sm font-semibold text-gray-700 dark:text-gray-300 mb-2">
                Ceritakan Proyek Anda *
              </label>
              <div class="relative">
                <div class="absolute top-3 left-4 pointer-events-none">
                  <MessageSquare :size="18" class="text-blue-500" />
                </div>
                <textarea id="message" v-model="form.message" required rows="5"
                  class="w-full pl-11 pr-4 py-3.5 border-2 border-gray-200 dark:border-gray-600 bg-white dark:bg-gray-700 text-gray-900 dark:text-white rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-blue-500 dark:focus:border-blue-400 outline-none transition-all resize-none"
                  placeholder="Ceritakan kebutuhan, target, dan timeline proyek Anda..."></textarea>
              </div>
            </div>

            <!-- Submit Button -->
            <button type="submit" :disabled="isSubmitting"
              class="group w-full bg-gradient-to-r from-purple-600 via-pink-500 to-orange-500 text-white py-4 rounded-xl font-bold text-lg hover:shadow-2xl hover:shadow-purple-500/50 transition-all transform hover:scale-[1.02] disabled:opacity-50 disabled:cursor-not-allowed disabled:transform-none flex items-center justify-center gap-2">
              <Send :size="20" class="group-hover:translate-x-1 transition-transform" />
              <span>{{ isSubmitting ? 'Mengirim Pesan...' : 'Kirim Pesan Sekarang' }}</span>
            </button>

            <p v-if="submitMessage" class="text-center text-sm"
              :class="submitSuccess ? 'text-green-600 dark:text-green-400' : 'text-red-600 dark:text-red-400'">
              {{ submitMessage }}
            </p>
          </form>
        </div>

        <!-- Contact Info & Social Media -->
        <div class="lg:col-span-2 space-y-6">
          <!-- Contact Cards -->
          <div class="grid grid-cols-1 gap-5">
            <!-- Email Card -->
            <div
              class="group bg-gradient-to-br from-blue-50 to-cyan-100 dark:bg-gray-800 rounded-2xl p-6 border-2 border-blue-200 dark:border-gray-700 hover:shadow-xl transition-all hover:-translate-y-1">
              <div class="flex items-start gap-4">
                <div
                  class="w-14 h-14 bg-gradient-to-br from-blue-500 to-cyan-600 rounded-xl flex items-center justify-center flex-shrink-0 shadow-lg group-hover:scale-110 transition-transform">
                  <Mail :size="24" class="text-white" />
                </div>
                <div class="flex-1">
                  <div class="font-bold text-gray-900 dark:text-white mb-1">Email</div>
                  <a href="mailto:dickaismaji@gmail.com"
                    class="text-blue-600 dark:text-blue-400 hover:text-blue-700 font-medium text-sm break-all">
                    dickaismaji@gmail.com
                  </a>
                </div>
              </div>
            </div>

            <!-- Phone Card -->
            <div
              class="group bg-gradient-to-br from-purple-50 to-pink-100 dark:bg-gray-800 rounded-2xl p-6 border-2 border-purple-200 dark:border-gray-700 hover:shadow-xl transition-all hover:-translate-y-1">
              <div class="flex items-start gap-4">
                <div
                  class="w-14 h-14 bg-gradient-to-br from-purple-500 to-pink-600 rounded-xl flex items-center justify-center flex-shrink-0 shadow-lg group-hover:scale-110 transition-transform">
                  <Phone :size="24" class="text-white" />
                </div>
                <div class="flex-1">
                  <div class="font-bold text-gray-900 dark:text-white mb-1">Telepon</div>
                  <a href="tel:+628515555555"
                    class="text-purple-600 dark:text-purple-400 hover:text-purple-700 font-medium text-sm">
                    +62 851 5555 555
                  </a>
                </div>
              </div>
            </div>

            <!-- Location Card -->
            <div
              class="group bg-gradient-to-br from-orange-50 to-yellow-100 dark:bg-gray-800 rounded-2xl p-6 border-2 border-orange-200 dark:border-gray-700 hover:shadow-xl transition-all hover:-translate-y-1">
              <div class="flex items-start gap-4">
                <div
                  class="w-14 h-14 bg-gradient-to-br from-orange-500 to-yellow-600 rounded-xl flex items-center justify-center flex-shrink-0 shadow-lg group-hover:scale-110 transition-transform">
                  <MapPin :size="24" class="text-white" />
                </div>
                <div class="flex-1">
                  <div class="font-bold text-gray-900 dark:text-white mb-1">Alamat</div>
                  <p class="text-gray-600 dark:text-gray-300 text-sm">
                    Klaten, Jawa Tengah,<br />
                    Indonesia
                  </p>
                </div>
              </div>
            </div>

            <!-- Hours Card -->
            <div
              class="group bg-gradient-to-br from-green-50 to-emerald-100 dark:bg-gray-800 rounded-2xl p-6 border-2 border-green-200 dark:border-gray-700 hover:shadow-xl transition-all hover:-translate-y-1">
              <div class="flex items-start gap-4">
                <div
                  class="w-14 h-14 bg-gradient-to-br from-green-500 to-emerald-600 rounded-xl flex items-center justify-center flex-shrink-0 shadow-lg group-hover:scale-110 transition-transform">
                  <Clock :size="24" class="text-white" />
                </div>
                <div class="flex-1">
                  <div class="font-bold text-gray-900 dark:text-white mb-1">Jam Kerja</div>
                  <p class="text-gray-600 dark:text-gray-300 text-sm">
                    Senin - Jumat: 09:00 - 18:00<br />
                    Sabtu: 09:00 - 15:00
                  </p>
                </div>
              </div>
            </div>
          </div>

          <!-- Social Media Links -->
          <div
            class="bg-gradient-to-br from-white to-pink-50/30 dark:bg-gray-800 rounded-2xl p-6 border-2 border-pink-200/50 dark:border-gray-700 shadow-xl">
            <h4 class="font-bold text-gray-900 dark:text-white mb-4 flex items-center gap-2">
              <Globe :size="20" class="text-pink-500" />
              <span>Follow Us</span>
            </h4>
            <div class="grid grid-cols-2 gap-3">
              <a href="https://twitter.com/dickaismaji" target="_blank" rel="noopener noreferrer"
                class="flex items-center gap-2 px-4 py-3 bg-gradient-to-r from-sky-400 to-sky-500 text-white rounded-xl hover:shadow-lg hover:scale-105 transition-all text-sm font-semibold">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z" />
                </svg>
                Twitter
              </a>
              <a href="https://instagram.com/dickaismaji" target="_blank" rel="noopener noreferrer"
                class="flex items-center gap-2 px-4 py-3 bg-gradient-to-r from-pink-500 to-rose-600 text-white rounded-xl hover:shadow-lg hover:scale-105 transition-all text-sm font-semibold">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913.306.788.717 1.459 1.384 2.126.667.666 1.336 1.079 2.126 1.384.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558.788-.306 1.459-.718 2.126-1.384.666-.667 1.079-1.335 1.384-2.126.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913-.306-.789-.718-1.459-1.384-2.126C21.319 1.347 20.651.935 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227-.224.562-.479.96-.899 1.382-.419.419-.824.679-1.38.896-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421-.569-.224-.96-.479-1.379-.899-.421-.419-.69-.824-.9-1.38-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678c-3.405 0-6.162 2.76-6.162 6.162 0 3.405 2.76 6.162 6.162 6.162 3.405 0 6.162-2.76 6.162-6.162 0-3.405-2.76-6.162-6.162-6.162zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405c0 .795-.646 1.44-1.44 1.44-.795 0-1.44-.646-1.44-1.44 0-.794.646-1.439 1.44-1.439.793-.001 1.44.645 1.44 1.439z" />
                </svg>
                Instagram
              </a>
              <a href="https://linkedin.com/in/dickaismaji" target="_blank" rel="noopener noreferrer"
                class="flex items-center gap-2 px-4 py-3 bg-gradient-to-r from-blue-600 to-blue-700 text-white rounded-xl hover:shadow-lg hover:scale-105 transition-all text-sm font-semibold">
                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                  <path
                    d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z" />
                </svg>
                LinkedIn
              </a>
            </div>
          </div>

          <!-- Stats Box -->
          <div
            class="bg-gradient-to-br from-purple-600 via-pink-500 to-orange-500 rounded-2xl p-6 text-white shadow-2xl">
            <h4 class="font-bold text-lg mb-4">🎯 Response Time</h4>
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-white/90">Email</span>
                <span class="font-bold">
                  < 24 jam</span>
              </div>
              <div class="flex items-center justify-between">
                <span class="text-white/90">WhatsApp</span>
                <span class="font-bold">
                  < 1 jam</span>
              </div>
              <div class="flex items-center justify-between">
                <span class="text-white/90">Telepon</span>
                <span class="font-bold">Instant</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue';
import { Mail, Phone, MapPin, Clock, Globe, User, Briefcase, MessageSquare, ChevronDown, Send } from 'lucide-vue-next';

const isSubmitting = ref(false);
const submitMessage = ref('');
const submitSuccess = ref(false);

const form = reactive({
  name: '',
  email: '',
  phone: '',
  service: '',
  message: ''
});

const handleSubmit = async () => {
  isSubmitting.value = true;
  submitMessage.value = '';

  // Simulate form submission
  setTimeout(() => {
    isSubmitting.value = false;
    submitSuccess.value = true;
    submitMessage.value = 'Terima kasih! Pesan Anda telah terkirim. Kami akan menghubungi Anda segera.';

    // Reset form
    form.name = '';
    form.email = '';
    form.phone = '';
    form.service = '';
    form.message = '';

    // Clear message after 5 seconds
    setTimeout(() => {
      submitMessage.value = '';
    }, 5000);
  }, 1500);
};
</script>
