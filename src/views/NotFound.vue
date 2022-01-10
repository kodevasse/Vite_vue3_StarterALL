<template>
  <header class="bg-white shadow">
    <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
      <h1 class="text-3xl font-bold leading-tight text-gray-900">Not Found</h1>
    </div>
  </header>
</template>

<script>
import { defineComponent, computed, reactive } from "vue";
import { useHead } from "@vueuse/head";

export default defineComponent({
  setup() {
    const siteData = reactive({
      title: `My website`,
      description: `My beautiful website`,
    });

    useHead({
      // Can be static or computed
      title: computed(() => siteData.title),
      meta: [
        {
          name: `description`,
          content: computed(() => siteData.description),
        },
      ],
    });
  },
});
</script>
