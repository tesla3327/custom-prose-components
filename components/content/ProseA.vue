<template>
  <div class="group inline relative z-0">
    <NuxtLink :href="href" :target="target">
      <slot />
    </NuxtLink>
    <div
      v-if="isInternal"
      class="absolute transition-all duration-150 bottom-full left-1/2 transform -translate-x-1/2 w-[400px] opacity-0 group-hover:opacity-100 pointer-events-none"
    >
      <div
        class="relative bottom-3 w-content bg-white border border-gray-300 py-3 px-4 shadow-lg rounded-lg overflow-auto"
      >
        <div class="font-bold">{{ metadata.title }}</div>
        <div>{{ metadata.description }}</div>
      </div>
    </div>
    <span v-else class="text-xs text-gray-500 font-bold">
      ↗
    </span>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  href: {
    type: String,
    default: '',
  },
  target: {
    type: String,
    default: undefined,
    required: false,
  },
});

const isInternal = computed(() => {
  return props?.href?.startsWith('/') || false;
});

const nuxtApp = useNuxtApp();
const { data: metadata } = await useAsyncData(
  props.href,
  () => queryContent(props.href).findOne(),
  {
    dedupe: 'defer',
    getCachedData(key) {
      return (
        nuxtApp.static.data[key] ||
        nuxtApp.payload.data[key]
      );
    },
  }
);
</script>
