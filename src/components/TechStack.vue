<template>
    <section
        class="py-20 bg-gradient-to-br from-cyan-50 via-blue-50 to-purple-50 dark:from-gray-800 dark:to-gray-900 relative overflow-hidden">
        <!-- Decorative elements -->
        <div class="absolute inset-0 opacity-20 dark:opacity-5 pointer-events-none">
            <div
                class="absolute top-20 left-10 w-80 h-80 bg-gradient-to-br from-cyan-300 to-blue-400 rounded-full filter blur-3xl">
            </div>
            <div
                class="absolute bottom-20 right-10 w-80 h-80 bg-gradient-to-br from-purple-300 to-pink-400 rounded-full filter blur-3xl">
            </div>
        </div>
        <div class="container mx-auto px-4 relative z-10">
            <div class="text-center mb-16">
                <div
                    class="inline-flex items-center space-x-2 bg-gradient-to-r from-cyan-100 to-blue-100 dark:bg-primary-900/30 border-2 border-cyan-300 dark:border-primary-800 px-5 py-2.5 rounded-full shadow-lg shadow-cyan-200/50 dark:shadow-none mb-4">
                    <Layers :size="18" class="text-cyan-600 dark:text-primary-400" />
                    <span class="text-sm font-bold text-cyan-700 dark:text-primary-300">💻 Technology Stack</span>
                </div>
                <h2
                    class="text-3xl md:text-4xl font-bold bg-gradient-to-r from-cyan-600 via-blue-600 to-purple-600 bg-clip-text text-transparent dark:text-white mb-4">
                    Teknologi Yang Kami Kuasai
                </h2>
                <p class="text-lg text-gray-700 dark:text-gray-300 max-w-2xl mx-auto font-medium">
                    Kami menggunakan teknologi terkini untuk membangun solusi digital yang powerful dan scalable
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-12">
                <div v-for="(category, index) in techCategories" :key="index" :class="[
                    'rounded-2xl p-8 shadow-xl dark:shadow-primary-900/20 hover:shadow-2xl transition-all duration-300 group border-2',
                    index === 0 ? 'bg-gradient-to-br from-white to-cyan-50/50 dark:bg-gray-800 border-cyan-200/50 dark:border-gray-700' : '',
                    index === 1 ? 'bg-gradient-to-br from-white to-purple-50/50 dark:bg-gray-800 border-purple-200/50 dark:border-gray-700' : '',
                    index === 2 ? 'bg-gradient-to-br from-white to-green-50/50 dark:bg-gray-800 border-green-200/50 dark:border-gray-700' : ''
                ]">
                    <div class="flex items-center space-x-3 mb-6">
                        <div :class="[
                            'w-12 h-12 rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300 shadow-lg',
                            index === 0 ? 'bg-gradient-to-br from-cyan-400 to-blue-500 shadow-cyan-500/40' : '',
                            index === 1 ? 'bg-gradient-to-br from-purple-400 to-pink-500 shadow-purple-500/40' : '',
                            index === 2 ? 'bg-gradient-to-br from-green-400 to-emerald-500 shadow-green-500/40' : ''
                        ]">
                            <component :is="category.icon" :size="24" class="text-white" />
                        </div>
                        <h3 :class="[
                            'text-xl font-bold',
                            index === 0 ? 'bg-gradient-to-r from-cyan-600 to-blue-600 bg-clip-text text-transparent dark:text-white' : '',
                            index === 1 ? 'bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent dark:text-white' : '',
                            index === 2 ? 'bg-gradient-to-r from-green-600 to-emerald-600 bg-clip-text text-transparent dark:text-white' : ''
                        ]">{{ category.title }}</h3>
                    </div>

                    <div class="space-y-3">
                        <div v-for="(tech, idx) in category.technologies" :key="idx"
                            class="flex items-center space-x-3 p-3 bg-gray-50 dark:bg-gray-700 rounded-lg hover:bg-primary-50 dark:hover:bg-primary-900/30 transition-colors duration-200 group/tech">
                            <div
                                class="w-8 h-8 bg-white dark:bg-gray-600 rounded-lg flex items-center justify-center shadow-sm">
                                <component :is="tech.icon" />
                            </div>
                            <span class="font-medium text-gray-900 dark:text-white">{{ tech.name }}</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Tech Logos -->
            <div
                class="bg-white dark:bg-gray-800 rounded-2xl p-8 shadow-lg dark:shadow-primary-900/20 border border-gray-100 dark:border-gray-700">
                <p
                    class="text-center text-sm text-gray-500 dark:text-gray-400 mb-6 font-semibold uppercase tracking-wider">
                    Trusted
                    Technologies</p>
                <div class="grid grid-cols-3 md:grid-cols-6 gap-8 items-center">
                    <div v-for="(logo, index) in techLogos" :key="index"
                        class="flex items-center justify-center group cursor-pointer">
                        <div class="text-center">
                            <component :is="logo.icon"
                                class="group-hover:scale-110 transition-transform duration-300" />
                            <p class="text-xs text-gray-600 dark:text-gray-400 mt-2 font-medium">{{ logo.name }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { Layers, Code2, Database, Cloud } from 'lucide-vue-next';
import { Icon } from '@iconify/vue';
import { markRaw, h } from 'vue';

// Helper function to create Iconify icon component
const createIcon = (iconName: string) => markRaw({
    render: () => h(Icon, { icon: iconName, width: 18, height: 18 })
});

const createLogoIcon = (iconName: string) => markRaw({
    render: () => h(Icon, { icon: iconName, width: 40, height: 40 })
});

const techCategories = [
    {
        icon: markRaw(Code2),
        title: 'Frontend',
        technologies: [
            { name: 'React.js', icon: createIcon('logos:react') },
            { name: 'Vue.js', icon: createIcon('logos:vue') },
            { name: 'Next.js', icon: createIcon('logos:nextjs-icon') },
            { name: 'Tailwind CSS', icon: createIcon('logos:tailwindcss-icon') }
        ]
    },
    {
        icon: markRaw(Database),
        title: 'Backend',
        technologies: [
            { name: 'Laravel', icon: createIcon('logos:laravel') },
            { name: 'Node.js', icon: createIcon('logos:nodejs-icon') },
            { name: 'PHP', icon: createIcon('logos:php') },
            { name: 'MySQL', icon: createIcon('logos:mysql-icon') }
        ]
    },
    {
        icon: markRaw(Cloud),
        title: 'DevOps & Tools',
        technologies: [
            { name: 'Docker', icon: createIcon('logos:docker-icon') },
            { name: 'Git', icon: createIcon('logos:git-icon') },
            { name: 'AWS', icon: createIcon('logos:aws') },
            { name: 'Vercel', icon: createIcon('logos:vercel-icon') }
        ]
    }
];

const techLogos = [
    { name: 'React', icon: createLogoIcon('logos:react') },
    { name: 'Vue.js', icon: createLogoIcon('logos:vue') },
    { name: 'Laravel', icon: createLogoIcon('logos:laravel') },
    { name: 'WordPress', icon: createLogoIcon('logos:wordpress-icon') },
    { name: 'Node.js', icon: createLogoIcon('logos:nodejs-icon') },
    { name: 'Docker', icon: createLogoIcon('logos:docker-icon') }
];
</script>
