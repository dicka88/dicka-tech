<template>
    <section class="py-20 relative overflow-hidden">
        <!-- Bright Animated Background -->
        <div class="absolute inset-0 bg-gradient-to-br from-purple-600 via-pink-500 to-orange-500 dark:from-primary-800 dark:via-primary-900 dark:to-blue-950">
            <div
                class="absolute top-0 left-0 w-96 h-96 bg-gradient-to-br from-yellow-400 to-orange-500 dark:bg-blue-600 rounded-full mix-blend-multiply dark:mix-blend-screen filter blur-3xl opacity-40 dark:opacity-10 animate-blob">
            </div>
            <div
                class="absolute top-0 right-0 w-96 h-96 bg-gradient-to-br from-pink-400 to-purple-600 dark:bg-purple-600 rounded-full mix-blend-multiply dark:mix-blend-screen filter blur-3xl opacity-40 dark:opacity-10 animate-blob animation-delay-2000">
            </div>
            <div
                class="absolute bottom-0 left-1/2 w-96 h-96 bg-gradient-to-br from-cyan-400 to-blue-500 dark:bg-primary-600 rounded-full mix-blend-multiply dark:mix-blend-screen filter blur-3xl opacity-40 dark:opacity-10 animate-blob animation-delay-4000">
            </div>
        </div>

        <!-- Pattern Overlay -->
        <div class="absolute inset-0 opacity-10">
            <div class="absolute inset-0"
                style="background-image: url('data:image/svg+xml,%3Csvg width=\'60\' height=\'60\' viewBox=\'0 0 60 60\' xmlns=\'http://www.w3.org/2000/svg\'%3E%3Cg fill=\'none\' fill-rule=\'evenodd\'%3E%3Cg fill=\'%23ffffff\' fill-opacity=\'0.4\'%3E%3Cpath d=\'M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z\'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E');">
            </div>
        </div>

        <div class="container mx-auto px-4 relative z-10">
            <div class="max-w-4xl mx-auto text-center">
                <!-- Badge -->
                <div
                    class="inline-flex items-center space-x-2 bg-white/10 backdrop-blur-sm border border-white/20 px-4 py-2 rounded-full mb-6">
                    <Sparkles :size="18" class="text-white" />
                    <span class="text-sm font-semibold text-white">Siap Memulai Proyek Anda?</span>
                </div>

                <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6 leading-tight">
                    Mari Wujudkan Ide Digital Anda Bersama Kami
                </h2>

                <p class="text-lg md:text-xl text-white/90 mb-10 max-w-2xl mx-auto leading-relaxed">
                    Dapatkan konsultasi gratis dan penawaran terbaik untuk proyek website impian Anda.
                    Tim kami siap membantu mewujudkan visi digital bisnis Anda.
                </p>

                <div class="flex flex-col sm:flex-row gap-4 justify-center items-center mb-12">
                    <a href="#contact"
                        class="group bg-white text-primary-600 px-8 py-4 rounded-xl hover:shadow-2xl hover:shadow-white/20 transition-all transform hover:scale-105 font-semibold text-lg flex items-center space-x-2 shadow-xl">
                        <MessageCircle :size="20" />
                        <span>Konsultasi Gratis</span>
                        <ArrowRight :size="20" class="group-hover:translate-x-1 transition-transform" />
                    </a>
                    <a href="#portfolio"
                        class="group bg-transparent text-white px-8 py-4 rounded-xl border-2 border-white/30 hover:border-white hover:bg-white/10 transition-all font-semibold text-lg flex items-center space-x-2 backdrop-blur-sm">
                        <Eye :size="20" />
                        <span>Lihat Portfolio</span>
                    </a>
                </div>

                <!-- Stats or Features -->
                <div class="grid grid-cols-2 md:grid-cols-4 gap-6 pt-8 border-t border-white/20">
                    <div class="text-center">
                        <div class="text-3xl md:text-4xl font-bold text-white mb-2">150+</div>
                        <div class="text-white/80 text-sm">Proyek Selesai</div>
                    </div>
                    <div class="text-center">
                        <div class="text-3xl md:text-4xl font-bold text-white mb-2">120+</div>
                        <div class="text-white/80 text-sm">Klien Puas</div>
                    </div>
                    <div class="text-center">
                        <div class="text-3xl md:text-4xl font-bold text-white mb-2">5+</div>
                        <div class="text-white/80 text-sm">Tahun Pengalaman</div>
                    </div>
                    <div class="text-center">
                        <div class="text-3xl md:text-4xl font-bold text-white mb-2">98%</div>
                        <div class="text-white/80 text-sm">Kepuasan Klien</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Decorative Elements -->
        <div
            class="absolute bottom-0 left-0 right-0 h-px bg-gradient-to-r from-transparent via-white/50 to-transparent">
        </div>
    </section>
</template>

<script setup lang="ts">
import { Sparkles, MessageCircle, ArrowRight, Eye } from 'lucide-vue-next';
</script>

<style scoped>
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

.animate-blob {
    animation: blob 7s infinite;
}

.animation-delay-2000 {
    animation-delay: 2s;
}

.animation-delay-4000 {
    animation-delay: 4s;
}
</style>
