<template>
  <div class="-mx-8">
    <img
      class="rounded-xl shadow-lg w-full"
      :src="src"
      :alt="alt"
      :width="width / 4"
      :height="height / 4"
      @click="toggleLightbox"
    />
  </div>
  <Teleport to="body">
    <div
      v-if="showLightbox"
      class="z-10 fixed bottom-0 right-0 top-0 left-0 bg-black bg-opacity-50 flex items-center justify-center backdrop-blur-sm transition-all duration-300 p-8"
      :class="{
        'opacity-0': !transition,
        'opacity-100': transition,
      }"
      @click="toggleLightbox"
    >
      <img
        :src="src"
        :alt="alt"
        :width="width"
        :height="height"
      />
    </div>
  </Teleport>
</template>

<script setup lang="ts">
defineProps({
  src: {
    type: String,
    default: '',
  },
  alt: {
    type: String,
    default: '',
  },
  width: {
    type: [String, Number],
    default: undefined,
  },
  height: {
    type: [String, Number],
    default: undefined,
  },
});

const showLightbox = ref(false);
const transition = ref(false);

async function sleep(ms: number) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}

async function toggleLightbox() {
  if (showLightbox.value) {
    transition.value = false;
    await sleep(300);
    showLightbox.value = false;
  } else {
    showLightbox.value = true;
    await sleep(300);
    transition.value = true;
  }
}
</script>
