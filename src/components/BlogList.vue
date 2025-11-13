<template>
  <section class="py-16 bg-white dark:bg-gray-900">
    <div class="container mx-auto px-4">
      <!-- Search Bar -->
      <div class="max-w-2xl mx-auto mb-12">
        <div class="relative">
          <input v-model="searchQuery" type="text"
            placeholder="Cari artikel berdasarkan judul, kategori, atau konten..."
            class="w-full px-6 py-4 pr-12 rounded-lg border-2 border-gray-200 dark:border-gray-700 focus:border-primary-500 focus:ring-2 focus:ring-primary-200 outline-none transition-all text-gray-900 dark:text-white dark:bg-gray-800"
            @input="currentPage = 1" />
          <button
            class="absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400 hover:text-primary-600 dark:hover:text-primary-400 transition-colors">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
          </button>
        </div>
        <!-- Search Results Info -->
        <div v-if="searchQuery.trim()" class="mt-3 text-sm text-gray-600 dark:text-gray-400">
          Ditemukan <span class="font-semibold text-primary-600 dark:text-primary-400">{{ searchResults.length }}</span>
          artikel
          <button @click="searchQuery = ''"
            class="ml-2 text-primary-600 dark:text-primary-400 hover:text-primary-700 dark:hover:text-primary-300 underline font-medium">
            Clear
          </button>
        </div>
      </div>

      <!-- Category Filter -->
      <div class="flex flex-wrap gap-3 mb-12 justify-center">
        <button v-for="category in categories" :key="category" @click="selectedCategory = category; currentPage = 1"
          class="px-5 py-2 rounded-lg font-medium transition-all text-sm"
          :class="selectedCategory === category
            ? 'bg-primary-600 dark:bg-primary-700 text-white shadow-lg'
            : 'bg-gray-100 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-700 border border-gray-200 dark:border-gray-700'">
          {{ category }}
        </button>
      </div>

      <!-- No Results -->
      <div v-if="filteredPosts.length === 0" class="text-center py-16">
        <svg class="w-24 h-24 mx-auto text-gray-300 dark:text-gray-700 mb-4" fill="none" stroke="currentColor"
          viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M9.172 16.172a4 4 0 015.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
        </svg>
        <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Tidak Ada Hasil</h3>
        <p class="text-gray-600 dark:text-gray-400 mb-6">
          Tidak ditemukan artikel yang sesuai dengan pencarian Anda.
        </p>
        <button @click="searchQuery = ''; selectedCategory = 'Semua'"
          class="bg-primary-600 dark:bg-primary-700 text-white px-6 py-3 rounded-lg font-semibold hover:bg-primary-700 dark:hover:bg-primary-800 transition-colors">
          Reset Filter
        </button>
      </div>

      <!-- Blog Grid -->
      <div v-else class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-7xl mx-auto">
        <article v-for="post in filteredPosts" :key="post.id"
          class="bg-white dark:bg-gray-800 rounded-xl shadow-lg overflow-hidden hover:shadow-xl dark:shadow-primary-900/20 transition-all duration-300 transform hover:-translate-y-2 group border border-gray-100 dark:border-gray-700">
          <a :href="`/blog/${post.slug}`" class="block cursor-pointer" :aria-label="`Baca artikel: ${post.title}`">
            <!-- Image -->
            <div class="relative overflow-hidden aspect-video bg-gray-200">
              <img 
                :src="post.image" 
                :alt="post.title"
                width="800"
                height="450"
                loading="lazy"
                class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-300" />
              <div class="absolute top-4 left-4">
                <span class="bg-primary-600 text-white px-3 py-1 rounded-lg text-xs font-semibold">
                  {{ post.category }}
                </span>
              </div>
            </div>

            <!-- Content -->
            <div class="p-6">
              <div class="flex items-center gap-4 text-sm text-gray-500 dark:text-gray-400 mb-3">
                <span class="flex items-center gap-1">
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                  </svg>
                  {{ formatDate(post.date) }}
                </span>
                <span class="flex items-center gap-1">
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                  {{ post.readTime }}
                </span>
              </div>

              <h3
                class="text-xl font-bold text-gray-900 dark:text-white mb-3 line-clamp-2 group-hover:text-primary-600 dark:group-hover:text-primary-400 transition-colors">
                {{ post.title }}
              </h3>

              <p class="text-gray-600 dark:text-gray-300 mb-4 line-clamp-3">
                {{ post.excerpt }}
              </p>

              <div class="flex items-center justify-between">
                <span class="text-sm text-gray-500 dark:text-gray-400">{{ post.author }}</span>
                <span
                  class="text-primary-600 dark:text-primary-400 font-semibold group-hover:text-primary-700 dark:group-hover:text-primary-300 transition-colors flex items-center gap-2">
                  Baca Selengkapnya
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                  </svg>
                </span>
              </div>
            </div>
          </a>
        </article>
      </div>

      <!-- Pagination -->
      <div v-if="totalPages > 1" class="flex justify-center gap-2 mt-12">
        <button @click="currentPage = currentPage - 1" :disabled="currentPage === 1"
          class="px-4 h-10 rounded-lg font-medium transition-all"
          :class="currentPage === 1
            ? 'bg-gray-100 dark:bg-gray-800 text-gray-400 cursor-not-allowed'
            : 'bg-gray-100 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-700'">
          ← Prev
        </button>
        <button v-for="page in totalPages" :key="page" @click="currentPage = page"
          class="w-10 h-10 rounded-lg font-medium transition-all"
          :class="currentPage === page
            ? 'bg-primary-600 dark:bg-primary-700 text-white'
            : 'bg-gray-100 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-700'">
          {{ page }}
        </button>
        <button @click="currentPage = currentPage + 1" :disabled="currentPage === totalPages"
          class="px-4 h-10 rounded-lg font-medium transition-all"
          :class="currentPage === totalPages
            ? 'bg-gray-100 dark:bg-gray-800 text-gray-400 cursor-not-allowed'
            : 'bg-gray-100 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-700'">
          Next →
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

interface Post {
  id: number;
  title: string;
  slug: string;
  excerpt: string;
  image: string;
  author: string;
  date: string;
  category: string;
  readTime: string;
}

const props = defineProps<{
  posts: Post[]
}>();

const searchQuery = ref('');
const selectedCategory = ref('Semua');
const currentPage = ref(1);
const postsPerPage = 9;

const categories = computed(() => {
  const cats = ['Semua', ...new Set(props.posts.map((post: Post) => post.category))];
  return cats;
});

// Filter posts by search query
const searchResults = computed(() => {
  if (!searchQuery.value.trim()) {
    return props.posts;
  }

  const query = searchQuery.value.toLowerCase().trim();
  return props.posts.filter((post: Post) => {
    return (
      post.title.toLowerCase().includes(query) ||
      post.excerpt.toLowerCase().includes(query) ||
      post.category.toLowerCase().includes(query) ||
      post.author.toLowerCase().includes(query)
    );
  });
});

// Apply category filter and pagination
const filteredPosts = computed(() => {
  let filtered = searchResults.value;

  if (selectedCategory.value !== 'Semua') {
    filtered = filtered.filter((post: Post) => post.category === selectedCategory.value);
  }

  const start = (currentPage.value - 1) * postsPerPage;
  const end = start + postsPerPage;

  return filtered.slice(start, end);
});

const totalPages = computed(() => {
  let filtered = searchResults.value;
  if (selectedCategory.value !== 'Semua') {
    filtered = filtered.filter((post: Post) => post.category === selectedCategory.value);
  }
  return Math.ceil(filtered.length / postsPerPage);
});

const formatDate = (dateString: string) => {
  const date = new Date(dateString);
  return new Intl.DateTimeFormat('id-ID', {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  }).format(date);
};
</script>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
