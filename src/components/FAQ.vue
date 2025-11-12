<template>
    <section id="faq" class="py-20 bg-gradient-to-br from-gray-50 to-blue-50 dark:from-gray-900 dark:to-gray-800">
        <div class="container mx-auto px-4">
            <div class="max-w-4xl mx-auto">
                <!-- Header -->
                <div class="text-center mb-12">
                    <h2 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-4">
                        Pertanyaan yang Sering Diajukan
                    </h2>
                    <p class="text-lg text-gray-600 dark:text-gray-300">
                        Temukan jawaban untuk pertanyaan umum tentang layanan kami
                    </p>
                </div>

                <!-- FAQ Items -->
                <div class="space-y-4">
                    <div v-for="(faq, index) in faqs" :key="index"
                        class="bg-white dark:bg-gray-800 rounded-xl shadow-md hover:shadow-lg transition-shadow border border-gray-200 dark:border-gray-700 overflow-hidden">
                        <button @click="toggleFAQ(index)"
                            class="w-full px-6 py-5 text-left flex items-center justify-between focus:outline-none focus:ring-2 focus:ring-primary-500 rounded-xl"
                            :aria-expanded="openIndex === index" :aria-controls="`faq-answer-${index}`">
                            <h3 class="text-lg font-semibold text-gray-900 dark:text-white pr-8">
                                {{ faq.question }}
                            </h3>
                            <svg class="w-6 h-6 text-primary-600 dark:text-primary-400 flex-shrink-0 transition-transform duration-300"
                                :class="{ 'rotate-180': openIndex === index }" fill="none" stroke="currentColor"
                                viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M19 9l-7 7-7-7" />
                            </svg>
                        </button>
                        <div :id="`faq-answer-${index}`" class="overflow-hidden transition-all duration-300"
                            :class="openIndex === index ? 'max-h-96 opacity-100' : 'max-h-0 opacity-0'">
                            <div class="px-6 pb-5 text-gray-600 dark:text-gray-300 leading-relaxed">
                                <p v-html="faq.answer"></p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const openIndex = ref<number | null>(null);

const toggleFAQ = (index: number) => {
    openIndex.value = openIndex.value === index ? null : index;
};

const faqs = [
    {
        question: 'Berapa lama waktu yang dibutuhkan untuk membuat website?',
        answer: 'Waktu pengerjaan website bervariasi tergantung kompleksitas dan fitur yang dibutuhkan. Website company profile sederhana biasanya selesai dalam 2-3 minggu, sedangkan website e-commerce atau aplikasi custom bisa memakan waktu 4-8 minggu. Kami akan memberikan timeline yang jelas di awal proyek.'
    },
    {
        question: 'Apakah website yang dibuat responsive dan mobile-friendly?',
        answer: 'Ya, semua website yang kami buat menggunakan <strong>mobile-first approach</strong> dan fully responsive. Website akan tampil sempurna di semua perangkat: desktop, tablet, dan smartphone. Ini penting untuk SEO dan user experience.'
    },
    {
        question: 'Apakah website sudah termasuk optimasi SEO?',
        answer: 'Ya, semua website yang kami buat sudah dioptimasi untuk SEO (Search Engine Optimization). Ini termasuk: meta tags, structured data, sitemap, fast loading speed, mobile-friendly, dan best practices lainnya. Kami juga menawarkan layanan SEO optimization terpisah untuk meningkatkan ranking di Google.'
    },
    {
        question: 'Platform apa saja yang digunakan untuk membuat website?',
        answer: 'Kami menggunakan berbagai teknologi modern sesuai kebutuhan: <strong>WordPress</strong> untuk website yang mudah dikelola, <strong>React/Next.js</strong> untuk aplikasi web modern, <strong>Laravel</strong> untuk aplikasi custom yang kompleks, dan <strong>Astro</strong> untuk website statis yang super cepat. Kami akan merekomendasikan teknologi terbaik untuk proyek Anda.'
    },
    {
        question: 'Apakah saya bisa mengelola konten website sendiri setelah selesai?',
        answer: 'Tentu saja! Kami akan memberikan <strong>training dan dokumentasi</strong> lengkap untuk mengelola website. Jika menggunakan WordPress, Anda bisa dengan mudah mengupdate konten melalui admin panel. Untuk website custom, kami akan membuat CMS yang user-friendly atau memberikan dokumentasi lengkap.'
    },
    {
        question: 'Berapa biaya untuk membuat website?',
        answer: 'Biaya pembuatan website bervariasi tergantung kebutuhan dan kompleksitas. Website company profile mulai dari <strong>Rp 5-10 juta</strong>, e-commerce mulai dari <strong>Rp 15-25 juta</strong>, dan aplikasi custom bisa lebih tinggi. Kami menyediakan paket yang fleksibel dan bisa disesuaikan dengan budget Anda. <a href="#contact" class="text-primary-600 hover:underline font-semibold">Hubungi kami</a> untuk konsultasi gratis dan penawaran yang sesuai kebutuhan Anda.'
    },
    {
        question: 'Apakah website sudah termasuk hosting dan domain?',
        answer: 'Hosting dan domain biasanya tidak termasuk dalam paket pembuatan website, namun kami bisa membantu Anda mendapatkan hosting dan domain yang sesuai. Kami merekomendasikan hosting yang reliable dan fast untuk performa optimal. Kami juga menawarkan paket maintenance yang termasuk hosting.'
    },
    {
        question: 'Apakah ada garansi atau support setelah website selesai?',
        answer: 'Ya, kami memberikan <strong>garansi 3 bulan</strong> untuk perbaikan bug dan support gratis. Setelah itu, kami menawarkan paket maintenance bulanan yang mencakup update, backup, security monitoring, dan support. Kami selalu siap membantu Anda kapan saja dibutuhkan.'
    },
    {
        question: 'Bisakah website diintegrasikan dengan sistem lain?',
        answer: 'Tentu! Kami bisa mengintegrasikan website dengan berbagai sistem seperti: payment gateway (Midtrans, Xendit), CRM, email marketing tools, Google Analytics, social media, dan sistem custom lainnya. Kami akan mendiskusikan kebutuhan integrasi di awal proyek.'
    },
    {
        question: 'Bagaimana proses pembayaran?',
        answer: 'Pembayaran biasanya dilakukan dengan sistem <strong>down payment 50%</strong> di awal proyek, dan <strong>50% sisanya</strong> setelah website selesai dan disetujui. Untuk proyek besar, bisa dibagi menjadi beberapa tahap pembayaran. Kami menerima transfer bank dan payment gateway.'
    }
];
</script>

<style scoped>
/* Smooth transitions */
.transition-all {
    transition-property: all;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
    transition-duration: 300ms;
}
</style>
