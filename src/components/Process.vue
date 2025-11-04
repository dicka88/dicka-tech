<template>
    <section id="process" class="py-20 bg-gradient-to-br from-yellow-50 via-orange-50 to-pink-50 dark:bg-gray-900 relative overflow-hidden">
        <!-- Decorative elements -->
        <div class="absolute inset-0 opacity-20 dark:opacity-5 pointer-events-none">
            <div class="absolute top-10 right-20 w-64 h-64 bg-gradient-to-br from-orange-300 to-yellow-400 rounded-full filter blur-3xl"></div>
            <div class="absolute bottom-10 left-20 w-64 h-64 bg-gradient-to-br from-pink-300 to-purple-400 rounded-full filter blur-3xl"></div>
        </div>
        <div class="container mx-auto px-4 relative z-10">
            <div class="text-center mb-16">
                <div
                    class="inline-flex items-center space-x-2 bg-gradient-to-r from-orange-100 to-yellow-100 dark:bg-primary-900/30 border-2 border-orange-300 dark:border-primary-800 px-5 py-2.5 rounded-full shadow-lg shadow-orange-200/50 dark:shadow-none mb-4">
                    <Workflow :size="18" class="text-orange-600 dark:text-primary-400" />
                    <span class="text-sm font-bold text-orange-700 dark:text-primary-300">⚡ Proses Kerja Kami</span>
                </div>
                <h2 class="text-3xl md:text-4xl font-bold bg-gradient-to-r from-orange-600 via-pink-600 to-purple-600 bg-clip-text text-transparent dark:text-white mb-4">
                    Bagaimana Kami Bekerja?
                </h2>
                <p class="text-lg text-gray-700 dark:text-gray-300 max-w-2xl mx-auto font-medium">
                    Proses pengerjaan proyek yang terstruktur dan transparan untuk hasil maksimal
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div v-for="(step, index) in steps" :key="index" class="relative group">
                    <!-- Connecting Line -->
                    <div v-if="index < steps.length - 1"
                        class="hidden lg:block absolute top-16 left-1/2 w-full h-0.5 bg-gradient-to-r from-primary-200 to-primary-300 z-0">
                    </div>

                    <!-- Step Card -->
                    <div class="relative z-10 text-center">
                        <!-- Number Badge -->
                        <div class="w-32 h-32 mx-auto mb-6 relative">
                            <div
                                class="absolute inset-0 bg-gradient-to-br from-primary-200 to-primary-100 rounded-2xl transform rotate-6 group-hover:rotate-12 transition-transform duration-300">
                            </div>
                            <div
                                :class="[
                                    'absolute inset-0 rounded-2xl shadow-xl dark:shadow-primary-900/20 flex items-center justify-center group-hover:shadow-2xl transition-all duration-300 border-2',
                                    index === 0 ? 'bg-gradient-to-br from-blue-50 to-cyan-100 dark:bg-gray-800 border-blue-200 dark:border-gray-700' : '',
                                    index === 1 ? 'bg-gradient-to-br from-purple-50 to-pink-100 dark:bg-gray-800 border-purple-200 dark:border-gray-700' : '',
                                    index === 2 ? 'bg-gradient-to-br from-orange-50 to-yellow-100 dark:bg-gray-800 border-orange-200 dark:border-gray-700' : '',
                                    index === 3 ? 'bg-gradient-to-br from-green-50 to-emerald-100 dark:bg-gray-800 border-green-200 dark:border-gray-700' : ''
                                ]">
                                <div class="text-center">
                                    <component :is="step.icon" :size="32" 
                                        :class="[
                                            'mx-auto mb-2',
                                            index === 0 ? 'text-blue-600 dark:text-primary-400' : '',
                                            index === 1 ? 'text-purple-600 dark:text-primary-400' : '',
                                            index === 2 ? 'text-orange-600 dark:text-primary-400' : '',
                                            index === 3 ? 'text-green-600 dark:text-primary-400' : ''
                                        ]" />
                                    <span :class="[
                                        'text-2xl font-bold',
                                        index === 0 ? 'text-blue-700 dark:text-white' : '',
                                        index === 1 ? 'text-purple-700 dark:text-white' : '',
                                        index === 2 ? 'text-orange-700 dark:text-white' : '',
                                        index === 3 ? 'text-green-700 dark:text-white' : ''
                                    ]">{{ index + 1 }}</span>
                                </div>
                            </div>
                        </div>

                        <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-3">{{ step.title }}</h3>
                        <p class="text-gray-600 dark:text-gray-300 text-sm leading-relaxed">{{ step.description }}</p>
                    </div>
                </div>
            </div>

            <!-- Timeline View for Mobile -->
            <div class="lg:hidden mt-12 space-y-6">
                <div v-for="(step, index) in steps" :key="`mobile-${index}`" class="flex gap-4">
                    <div class="flex flex-col items-center">
                        <div
                            class="w-12 h-12 bg-gradient-to-br from-primary-600 to-primary-800 rounded-full flex items-center justify-center text-white font-bold shadow-lg shadow-primary-500/40">
                            {{ index + 1 }}
                        </div>
                        <div v-if="index < steps.length - 1" class="w-0.5 flex-1 bg-primary-200 my-2"></div>
                    </div>
                    <div class="flex-1 pb-8">
                        <div class="bg-white dark:bg-gray-800 rounded-xl p-6 shadow-md dark:shadow-primary-900/20 border border-gray-100 dark:border-gray-700">
                            <component :is="step.icon" :size="24" class="text-primary-600 dark:text-primary-400 mb-3" />
                            <h3 class="text-lg font-bold text-gray-900 dark:text-white mb-2">{{ step.title }}</h3>
                            <p class="text-gray-600 dark:text-gray-300 text-sm">{{ step.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { Lightbulb, PenTool, Code2, Rocket, Workflow } from 'lucide-vue-next';
import { markRaw } from 'vue';

const steps = [
    {
        icon: markRaw(Lightbulb),
        title: 'Discovery & Planning',
        description: 'Kami mendengarkan kebutuhan Anda dan merencanakan strategi terbaik untuk mencapai tujuan bisnis.'
    },
    {
        icon: markRaw(PenTool),
        title: 'Design & Prototype',
        description: 'Tim desain kami membuat mockup dan prototype yang sesuai dengan brand identity Anda.'
    },
    {
        icon: markRaw(Code2),
        title: 'Development',
        description: 'Developer berpengalaman kami mengubah desain menjadi website yang fungsional dan responsif.'
    },
    {
        icon: markRaw(Rocket),
        title: 'Launch & Support',
        description: 'Setelah testing menyeluruh, kami launch website Anda dan memberikan support berkelanjutan.'
    }
];
</script>

<style scoped>
/* Additional animations if needed */
</style>
